# Aesthetic Personality System

Use a 4-axis, 16-type personality code. This is a preference portrait, not an ability score.

## Axes

| Axis | Left | Right | Derived from |
| --- | --- | --- | --- |
| 1 | `S` Sensuous / 感性直觉 | `C` Conceptual / 观念解释 | D1+D5 versus D4+D6 |
| 2 | `O` Ordered / 秩序平衡 | `T` Tensional / 张力冲突 | formal harmony versus contrast, rupture, ambiguity |
| 3 | `H` Heritage / 历史谱系 | `X` eXperimental / 实验越界 | D6 tradition/category versus D4 experimentation/category break |
| 4 | `I` Intimate / 私密内向 | `M` Monumental / 崇高公共 | quiet, close, bodily, domestic versus scale, publicness, monumentality |

## 16 Types

| Type | Chinese name | One-line direction |
| --- | --- | --- |
| `SOHI` | 温润古典者 | 被有秩序、有人情、带历史温度的美吸引。 |
| `SOHM` | 殿堂凝视者 | 喜欢宏大而稳定的经典气场。 |
| `SOXI` | 微光实验者 | 偏爱感性、轻微越界、贴近身体的实验。 |
| `SOXM` | 感官造境者 | 容易被沉浸式、感官丰富的场域吸引。 |
| `STHI` | 残痕叙事者 | 喜欢有伤痕、有记忆、有身体张力的作品。 |
| `STHM` | 悲壮考古者 | 被历史冲突和宏大情绪中的力量打动。 |
| `STXI` | 异质采样者 | 喜欢材料碰撞、边缘经验和细碎异质感。 |
| `STXM` | 感官风暴者 | 被强冲突、强现场、强刺激的先锋经验吸引。 |
| `COHI` | 文脉读图者 | 倾向从秩序、图像学和文化线索中进入作品。 |
| `COHM` | 秩序策展者 | 喜欢宏观结构清晰、观念与历史互相支撑的作品。 |
| `COXI` | 冷静发明者 | 偏爱克制、聪明、形式清晰的观念实验。 |
| `COXM` | 观念纪念碑 | 被大型观念结构、制度议题和公共叙事吸引。 |
| `CTHI` | 暗线考据者 | 喜欢历史暗线、隐喻冲突和可反复解释的作品。 |
| `CTHM` | 历史辩论者 | 关注传统、权力、公共记忆之间的冲突。 |
| `CTXI` | 边界解码者 | 对暧昧、混杂、反类型的小型实验敏感。 |
| `CTXM` | 先锋宣言者 | 喜欢高观念密度、高冲突、公共姿态强的作品。 |

## Portrait Prompt Rules

For detailed 16-type visual identities, load `personality-visual-system.md`.

Generate a portrait prompt for each type instead of drawing a fake avatar in code.

Base prompt:

> A refined artistic half-body portrait representing an aesthetic personality type, contemporary exhibition poster quality, painterly but clean, expressive clothing and posture, no text, no logos, no cartoon mascot, sophisticated museum color palette.

Axis modifiers:

- `S`: tactile materials, warm skin light, visible texture.
- `C`: precise geometry, symbolic props, intellectual gaze.
- `O`: balanced composition, calm symmetry, controlled rhythm.
- `T`: asymmetric tension, diagonal force, fractured background.
- `H`: archival tones, historical fabric, subtle art-historical references.
- `X`: experimental materials, hybrid silhouette, unexpected color relation.
- `I`: close crop, quiet interior mood, intimate scale.
- `M`: larger scale, public aura, monumental posture.

## Aggregation Rules

- Use all analyzed artworks, not only the highest-scoring one.
- Let the user override a work identity without changing the visual aesthetic evidence.
- If the sample has fewer than 5 artworks, mark personality confidence as medium or low.
- If axes are close, mention the secondary tendency in the card copy.
