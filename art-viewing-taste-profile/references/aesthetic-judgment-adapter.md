# Aesthetic Judgment Adapter

This Skill adapts the user's `aesthetic-judgment` framework for art-viewing taste profiles. Keep the full reasoning rigorous; present only concise results to users.

## Eight Hidden Dimensions

Score each dimension from 0 to 5 and attach evidence.

| Code | Dimension | Core question |
| --- | --- | --- |
| D1 | Sensory presence / 感性呈现 | Does it first work on the senses? |
| D2 | Formal organization / 形式组织 | Do parts form a strong whole? |
| D3 | Medium and craft / 媒介工艺 | Does it understand and use its medium well? |
| D4 | Meaning and imagination / 意义想象 | Does it open sustained interpretation? |
| D5 | Affect and embodiment / 情感身体 | Does it create precise embodied feeling? |
| D6 | History and category / 历史范畴 | Does it understand tradition, type, and institution? |
| D7 | Life, function, ethics / 生活伦理 | Is it appropriate in real use and shared life? |
| D8 | Vitality and afterlife / 生命余韵 | Does it reward return and memory? |

## Default Domain Weights

Use these when judging exhibition artworks.

| Domain | D1 | D2 | D3 | D4 | D5 | D6 | D7 | D8 |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| Contemporary art | 10 | 15 | 10 | 20 | 15 | 20 | 5 | 5 |
| Painting / photography / visual image | 20 | 20 | 15 | 15 | 10 | 10 | 5 | 5 |

## Frontstage Output

Show:

- one-sentence aesthetic judgment;
- 3-5 aesthetic keywords;
- strongest quality with visible evidence;
- one limitation or alternative reading;
- confidence.

Do not show a large score table on the first screen. The card must feel like insight, not homework.

## Reasoning Rules

- Describe before judging.
- Bind each aesthetic word to observable details.
- Use comparison when possible: peer works, genre conventions, historical precedents, or exhibition context.
- Separate preference from judgment. The system can infer what the user likes, but should not rank the user's taste.
