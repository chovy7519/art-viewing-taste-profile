# Skill Flowchart

Use this file when explaining, pitching, or implementing the Art Viewing Taste Profile Skill as an agent workflow or product flow.

## Main Workflow

```mermaid
flowchart TD
  A["用户上传观展照片"] --> B{"是否提供展览/展签/地点线索？"}
  B -->|仅照片| C["生成中性视觉描述"]
  B -->|有上下文| D["读取 OCR、展览信息、用户补充"]
  D --> C

  C --> E["生成作品候选"]
  E --> F["为每个候选附证据与置信度"]
  F --> G{"证据是否足够？"}
  G -->|足够| H["选择 probable / confirmed 作品"]
  G -->|不足| I["标记 unidentified，仅保留视觉描述"]
  H --> J["ArtworkRecord"]
  I --> J

  J --> K["8 维审美判断隐藏推理"]
  K --> L["前台输出：一句判断、关键词、证据、局限、置信度"]
  K --> M["聚合所有作品判断"]
  M --> N["4 轴偏好计算：S/C、O/T、H/X、I/M"]
  N --> O["生成 16 型审美人格"]
  O --> P["人格卡文案、代表作品、画像 prompt"]

  P --> Q{"是否需要视觉或传播资产？"}
  Q -->|不需要| R["交付作品卡 + 审美判断 + 审美画像"]
  Q -->|人格视觉| S["加载 personality-visual-system.md"]
  Q -->|小红书/比赛包装| T["加载 xiaohongshu-assets.md"]
  S --> R
  T --> R
```

## Recognition Subflow

```mermaid
flowchart TD
  A["单张作品照片"] --> B["视觉描述：媒介、主体、构图、颜色、文字、空间语境"]
  B --> C["候选生成：视觉线索 + OCR + 展览上下文 + 可用搜索"]
  C --> D["候选证据表"]
  D --> E{"候选身份是否可靠？"}
  E -->|可靠来源或用户确认| F["confirmed"]
  E -->|较可信但未确认| G["probable"]
  E -->|只有风格相似或证据弱| H["unidentified"]
  F --> I["selected_work"]
  G --> I
  H --> J["visual_description only"]
  I --> K{"用户是否修正？"}
  J --> K
  K -->|是| L["user_edited"]
  K -->|否| M["保持当前识别状态"]
  L --> N["ArtworkRecord"]
  M --> N
```

## Output Data Structure

```mermaid
flowchart LR
  A["输入照片集"] --> B["ArtworkRecord[]"]
  B --> C["AestheticJudgment[]"]
  C --> D["AestheticPersonality"]

  B --> B1["image path"]
  B --> B2["visual description"]
  B --> B3["recognition status"]
  B --> B4["candidates / selected work / user override"]

  C --> C1["D1-D8 hidden scores"]
  C --> C2["dominant dimensions"]
  C --> C3["aesthetic terms + evidence"]
  C --> C4["alternative reading + confidence"]

  D --> D1["4-letter type code"]
  D --> D2["axis scores"]
  D --> D3["Chinese type name + verdict"]
  D --> D4["representative works + share card copy"]
```

## Product Notes

| Step | Product meaning | Key risk |
| --- | --- | --- |
| 作品识别 | 把凌乱相册变成可解释作品卡 | 识别幻觉，尤其是无展签、局部图、装置/影像作品 |
| 审美判断 | 把作品从“叫什么”推进到“为什么吸引你” | 审美词空泛，证据不能回到可观察细节 |
| 人格聚合 | 从单件作品判断上升到用户偏好结构 | 样本过少时结论过度确定 |
| 视觉/传播包装 | 把分析结果变成可分享的卡片和招募素材 | 包装压过核心能力，变成泛泛人格测试 |

## MVP Cut

1. MVP 1: only support photo upload, visual description, candidate recognition, and editable `ArtworkRecord`.
2. MVP 2: add concise aesthetic judgment cards with visible evidence and confidence.
3. MVP 3: aggregate at least 5 artworks into a 4-axis / 16-type taste profile.
4. MVP 4: generate share card copy, portrait prompt, and Xiaohongshu cover/recording assets.
