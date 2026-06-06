# Personality Visual System

Use this file when designing the 16 aesthetic personality characters for cards, Xiaohongshu covers, posters, or generated image prompts.

## Art Direction V3

Create a coherent **MBTI-style hand-drawn character sheet** for aesthetic personalities. The style should reference the user's examples structurally: white background, square portrait cells, low-detail hand-drawn characters, readable silhouettes, limited color families, playful props, and label space. It should not look like polished AI anime or semi-realistic portrait rendering.

This is not a solemn museum portrait system. It is a social-media-friendly character IP system for sharing aesthetic personality results. The original IP direction is **"gallery sprites"**: small rounded human-like art spirits who carry exhibition, archive, making, and interpretation tools.

Global constraints:

- Use 4x4 square cards or rounded-rectangle frames.
- Character style: loose hand-drawn sticker illustration, uneven ink line, flat color blocks, soft marker wash, small intentional imperfections.
- Keep each character rounded, iconic, approachable, and easy to recognize at small size.
- Use white or very light background with simple soft color aura per family.
- Use art-viewing / art-making props: sketchbook, gallery map, magnifier, camera, tiny sculpture, color swatch, thread, acrylic sheet, headphones, archive folder.
- Type letters and Chinese names should be overlaid by the UI/design layer, not generated inside the image.
- Avoid photorealism, AI anime gloss, perfect faces, complex hair rendering, oil-paint portrait, heavy museum drama, fantasy costume, luxury fashion editorial, and generic stock-avatar beauty.
- Do not make all faces identical. Vary silhouette, eye shape, posture, prop scale, and small accessories.
- Do not over-render. Prefer graphic economy: 2-3 colors per character, simple shadows, visible white space.

## Visual Families

Use four color families to echo MBTI reference sheets while mapping to the aesthetic axes:

| Family | Types | Color cue | Feel |
| --- | --- | --- | --- |
| Warm classical | `SOH*` | jade, cream, soft olive | gentle, orderly, historical |
| Warm experimental | `SOX*` + `STX*` | coral, yellow, teal accents | sensory, playful, inventive |
| Cool conceptual | `COH*` + `COX*` | blue, grey, black, transparent acrylic | analytic, structured, curatorial |
| Dark tension | `STH*` + `CT*` | plum, rust, charcoal, red thread | dramatic, archival, interpretive |

## Axis Visual Language

| Axis | Visual cue |
| --- | --- |
| `S` Sensuous | softer face, tactile clothes, flowers/fabric/color swatches, warmer coloring |
| `C` Conceptual | glasses, books, diagrams, archive folders, geometric props, cooler coloring |
| `O` Ordered | neat pose, centered framing, tidy clothing, stable gaze |
| `T` Tensional | tilted pose, sharper expression, asymmetrical clothes, motion marks |
| `H` Heritage | classical patterns, museum map, archive paper, muted historical palette |
| `X` eXperimental | translucent materials, odd tools, playful color accents, hybrid accessories |
| `I` Intimate | close crop, inward gesture, small handheld object, quiet expression |
| `M` Monumental | open gesture, confident posture, larger prop/background shape, public energy |

## 16 Character Concepts

| Type | Name | Character direction |
| --- | --- | --- |
| `SOHI` | 温润古典者 | Round jade gallery sprite, small robe-like scarf, holding a folded gallery map and ceramic token, gentle centered pose. |
| `SOHM` | 殿堂凝视者 | Cream-and-gold sprite with tiny cape and hand microphone, upright public pose, simple spotlight circle. |
| `SOXI` | 微光实验者 | Pale yellow translucent scarf sprite, holding three glowing material chips, shy curious pose. |
| `SOXM` | 感官造境者 | Bright teal-orange sprite with color swatches, both arms open, simple light ribbon behind. |
| `STHI` | 残痕叙事者 | Beige patched sprite with red thread and worn notebook, quiet side glance, paper scraps. |
| `STHM` | 悲壮考古者 | Bronze-black sprite with archive photo cards, diagonal cloak shape, solemn eyes. |
| `STXI` | 异质采样者 | Patchwork sprite with found-object charms and small sample bag, alert sideways pose. |
| `STXM` | 感官风暴者 | Paint-splashed sprite with big brush, tilted jumping pose, controlled color burst. |
| `COHI` | 文脉读图者 | Blue-grey glasses sprite, magnifier and open book, careful reading pose. |
| `COHM` | 秩序策展者 | Navy curator sprite with clipboard/floor-plan board, neat centered authority pose. |
| `COXI` | 冷静发明者 | Minimal black sprite with transparent acrylic plate and tiny geometric hairpin, focused gaze. |
| `COXM` | 观念纪念碑 | Structured blue-grey sprite holding a cube model, confident presenter gesture. |
| `CTHI` | 暗线考据者 | Dark plum sprite with red thread map and archive scraps, intense close-reading eyes. |
| `CTHM` | 历史辩论者 | Charcoal-rust sprite with layered documents, one sharp debating hand gesture. |
| `CTXI` | 边界解码者 | Soft purple translucent sprite with coded fragments and mixed collar, shy but sharp gaze. |
| `CTXM` | 先锋宣言者 | Black-red manifesto sprite with poster fragments, bold pointing pose, high-contrast aura. |

## Master Contact Sheet Prompt

Use this for a 4x4 visual board.

```text
Use case: stylized-concept
Asset type: 4x4 hand-drawn MBTI-style character design contact sheet for an art-viewing taste profile system
Primary request: Create sixteen original "gallery sprite" characters for sixteen aesthetic personality types. Arrange them in a clean 4 by 4 grid of square portrait cards. Leave blank space below each character for labels, but do not draw any letters, words, logos, or readable text.
Style: hand-drawn sticker character sheet, loose uneven ink outline, flat color blocks, soft marker wash, visible sketchy imperfections, white background, rounded card frames, cute but not childish, original art-culture mascot system, graphic economy, not polished AI anime.
Shared system: small rounded human-like art spirits, clear silhouette, simple expressive eyes, 2-3 colors per character, art-viewing or art-making props, consistent card layout, lots of white space.
Row 1: jade gallery sprite with folded map and ceramic token; cream-gold public sprite with tiny cape and microphone under spotlight; pale yellow translucent sprite with glowing material chips; teal-orange sensory sprite with color swatches and light ribbon.
Row 2: beige patched sprite with red thread and worn notebook; bronze-black archive sprite with photo cards and diagonal cloak; patchwork sample-collector sprite with charms and bag; paint-splashed sprite jumping with big brush.
Row 3: blue-grey glasses sprite with magnifier and book; navy curator sprite with floor-plan clipboard; minimal black inventor sprite with transparent acrylic plate; structured blue-grey presenter sprite holding a cube model.
Row 4: dark plum close-reader sprite with red-thread map; charcoal-rust debate sprite with layered documents; soft purple boundary-decoder sprite with coded fragments; black-red manifesto sprite pointing with poster scraps.
Composition: balanced 4x4 grid, each card distinct but clearly same family, ample white margins, hand-made sticker/character-sheet feel, Xiaohongshu friendly, original and not copied from MBTI references.
Avoid: text, labels, letters, logos, photorealism, semi-realistic anime faces, glossy AI rendering, perfect symmetrical beauty faces, complex hair highlights, solemn oil portrait, overdecorated fantasy costume, stock-avatar look, cluttered backgrounds.
```

## Individual Prompt Template

```text
Use case: stylized-concept
Asset type: hand-drawn aesthetic personality sprite for a share card
Primary request: Create one original gallery-sprite character representing {TYPE} {NAME}. Leave blank label space; do not draw any text, letters, logos, or labels.
Style: hand-drawn sticker character, loose uneven ink outline, flat color blocks, soft marker wash, visible sketchy imperfections, white rounded card frame, cute but not childish, original art-culture mascot system.
Subject: small rounded human-like art spirit, clear silhouette, simple expressive eyes, 2-3 colors, art-viewing or art-making props.
Visual direction: {CHARACTER_DIRECTION}
Shared system: lots of white space, soft color aura, clean white card, hand-made sticker feel, suitable for Xiaohongshu personality result sharing.
Avoid: text, logos, letters, photorealism, semi-realistic anime face, glossy AI rendering, solemn oil portrait, fantasy costume, stock-avatar look.
```
