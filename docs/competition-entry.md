# Art Viewing Taste Profile / 观展审美画像

Competition entry notes for the Skill-first prototype.

## One-Sentence Pitch

把看展时拍下的一组作品照片，转化为可校正的作品卡、基于证据的审美判断，以及可分享的个人观展审美画像。

## Problem

观展照片是一个很真实但被低估的数据入口。用户在展览中拍下的作品，不只是资料记录，也包含他们的观看选择、注意力停留和审美偏好。

现有工具的缺口在于：

- 相册工具只能管理图片，不能理解作品和观看选择；
- 通用视觉模型容易把相似风格误认成具体作品；
- 艺术评论语言门槛高，普通用户很难把“喜欢”转化为可解释的审美语言；
- 社交分享缺少一个既有趣又不肤浅的结果形态。

## Solution

Art Viewing Taste Profile 用 Skill 的方式定义一个可复用工作流：

1. 从观展照片生成中性视觉描述。
2. 识别可能的作品候选，并为候选附上证据和置信度。
3. 在证据不足时安全回退到 `unidentified`，允许用户手动修正。
4. 用 8 维审美框架进行隐藏推理，前台输出简洁判断。
5. 聚合多件作品，生成 4 轴 / 16 型审美画像。
6. 输出作品卡、人格卡、头像 prompt 和小红书传播素材。

## Why It Fits A Skill

这个项目目前不应该优先做成重型 App。更低成本、也更适合参赛验证的形态是 Skill：

- 规则复杂但界面可以先很轻；
- 作品识别需要强约束，避免模型自由发挥；
- 审美判断需要稳定的推理框架，而不是每次临场写评论；
- 传播资产可以作为包装层，但核心价值在工作流本身。

## Technical Path

| Layer | Prototype choice | Production direction |
| --- | --- | --- |
| Skill runtime | Agent host capabilities for vision, OCR, file reading, and search | Keep Skill agent-agnostic; add adapters for specific runtimes |
| Image understanding | Multimodal model visual description | Add batch upload, OCR extraction, EXIF/context capture |
| Artwork recognition | Candidate generation with confidence and evidence | Add curated museum/exhibition source retrieval and user correction history |
| Aesthetic judgment | 8 hidden dimensions with concise frontstage output | Add evaluation examples and domain-specific weighting |
| Taste profile | 4 axes / 16 types | Add confidence calibration and secondary tendencies |
| Interface | Skill output and social cards | Lightweight web app for upload, review, edit, export |

## MVP Scope

### MVP 1: Evidence-First Artwork Cards

- Upload or provide 5-20 exhibition photos.
- Generate neutral visual descriptions.
- Produce candidates, evidence, confidence, and recognition status.
- Allow user override.

### MVP 2: Aesthetic Judgment Cards

- Generate one-sentence aesthetic judgment for each work.
- Show 3-5 keywords with visible evidence.
- Include one alternative reading or limitation.

### MVP 3: Taste Profile

- Aggregate at least 5 analyzed works.
- Output 4-axis scores and one type code.
- Generate Chinese type name, verdict, and representative works.

### MVP 4: Shareable Assets

- Generate personality card copy.
- Generate portrait prompt based on type.
- Generate Xiaohongshu cover logic and 30-second demo script.

## Risks And Guardrails

| Risk | Why it matters | Guardrail |
| --- | --- | --- |
| Artwork hallucination | Wrong title/artist damages trust immediately | Require evidence, source URL when available, and `unidentified` fallback |
| Overclaiming personality | Small photo samples cannot prove stable personality | Treat result as preference portrait, not ability score or fixed identity |
| Empty aesthetic language | Generic adjectives feel like AI filler | Bind every term to visual, material, formal, emotional, or contextual evidence |
| Packaging over substance | Social cards can turn it into a shallow test | Keep recognition, judgment, and profile workflow as the reusable core |

## Differentiation

This is not a photo album app, a pure artwork recognizer, or a generic MBTI-style game.

The distinctive part is the chain:

```text
观展照片 -> 作品证据 -> 审美判断 -> 偏好结构 -> 可分享画像
```

That chain makes the result entertaining enough for social sharing, but still anchored in evidence and art-viewing behavior.

## Next Iteration

1. Build a minimal web interface for image upload and result review.
2. Add editable `ArtworkRecord` cards.
3. Add exportable share-card templates.
4. Test with 20 seed users who frequently visit exhibitions.
5. Collect failure cases: misrecognition, weak evidence, boring judgment, confusing type copy.
6. Convert repeated failures into stronger Skill rules and examples.
