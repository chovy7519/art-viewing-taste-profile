---
name: art-viewing-taste-profile
description: "Use to turn art-viewing or exhibition photos into artwork recognition, evidence-backed aesthetic judgment, and 4-axis/16-type taste profile cards. Trigger for 观展助手, 展览照片整理, 作品识别, 审美判断, 审美人格, 审美画像, 艺术品味分析, gallery photos, museum photos, exhibition photo notes, artwork cards, or aesthetic personality results."
---

# Art Viewing Taste Profile

## Purpose

Build an agent-agnostic Skill for "观展审美画像": input photos a person took while viewing art, identify artwork candidates as evidence allows, judge their aesthetic traits, and infer what kind of beauty the viewer tends to notice.

The Skill is about the viewer's art-viewing selection and taste profile. It is not primarily about judging an exhibition's curatorial quality, and it is not a production photo-library app.

## Name Rationale

Use **Art Viewing Taste Profile / 观展审美画像** because the object is not "exhibition aesthetics" in general. The user's photos are treated as traces of viewing choices: what they stopped for, framed, saved, and wanted to remember. "Taste profile" also stays closer to aesthetic theory than "personality test": it describes preference structure without ranking the user's taste.

## Core Workflow

1. **Collect art-viewing photos**: use real photos from museums, biennales, galleries, art fairs, studios, public art, or other viewing contexts. Do not require wall-label photos; labels are optional evidence for correction.
2. **Use host capabilities**: rely on the current agent/runtime for image understanding, OCR, file reading, and web search. Do not require a model API configuration as part of the Skill's core workflow.
3. **Recognize artworks**: load `references/recognition-workflow.md`. Produce candidates, evidence, confidence, and a safe fallback to visual description when identity is uncertain.
4. **Judge aesthetics**: load `references/aesthetic-judgment-adapter.md`. Use the 8-dimension aesthetic framework as the hidden reasoning layer; show concise evidence-based judgments.
5. **Generate taste profile**: load `references/personality-system.md`. Convert aggregated judgments into one 4-letter type and card copy.
6. **Design profile visuals**: load `references/personality-visual-system.md` when the user needs the 16 visual identities, portrait prompts, cover art, or avatar direction.
7. **Prepare social or competition assets**: load `references/xiaohongshu-assets.md` only when the user needs post titles, cover logic, or a 30-second recording outline.

For workflow explanation, implementation planning, or product pitching, load `references/skill-flowchart.md`.

## Output Contract

Always preserve these output layers:

- `ArtworkRecord`: image path, visual description, recognition status, candidates, selected work, user override.
- `AestheticJudgment`: domain, D1-D8 scores, dominant dimensions, aesthetic terms, evidence, alternative reading, confidence.
- `AestheticPersonality`: type code, axis scores, Chinese type name, verdict, description, representative works, portrait prompt, share card copy.

## Quality Rules

- Keep the front stage confident but the data model honest: show "most likely" only when evidence supports it.
- Do not invent artwork identity, artist, year, collection, or source URL.
- Make every aesthetic word traceable to observable visual, material, formal, emotional, or contextual evidence.
- Do not evaluate the user as high/low taste. The card describes preference structure: "what kind of beauty attracts you."
- Treat competition and social-media output as packaging; the reusable Skill remains the art-viewing recognition, judgment, and taste-profile workflow.
