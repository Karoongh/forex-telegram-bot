# CHARACTER-LOCK — FX-TRADER-01

> Strict identity lock for the recurring fictional character FX-TRADER-01.
> This file is the operational enforcement document. It works together with:
> - docs/BRAND-VISUAL-IDENTITY.md (source of truth for appearance)
> - docs/IMAGE-GENERATION-WORKFLOW.md (how to generate)
> - TRADING-SCREEN-RULES.md (monitor / phone chart accuracy)
> - the character-identity-lock skill
> - the trading-screen-accuracy skill

## Status

**OFFICIALLY LOCKED — 2026-10-02**

Master Reference, Full-body Reference and Lifestyle Reference are approved.
Any future image that fails the checklist below must be rejected.

## Locked Identity (do not change)

- Character ID: `FX-TRADER-01`
- Fictional male, approximately 32 years old
- Middle Eastern / Mediterranean appearance
- Light olive skin
- Dark brown eyes
- Thick dark brown hair, naturally styled with subtle side part
- Short, well-groomed dark beard and mustache
- Natural eyebrows, straight medium-sized nose, defined but natural jawline
- Realistic facial asymmetry and skin texture/pores
- Approximately 180 cm
- Healthy, moderately athletic build with naturally broad shoulders
- Looks like a successful professional in his early 30s — not a fashion model or fitness influencer

## Approved Reference Images

| Role | Path |
|------|------|
| Master Reference (primary face lock) | `01-master-reference/FX-TRADER-01_master_reference_20260928_v01.jpg` |
| Full-body Reference | `02-full-body-reference/FX-TRADER-01_full_body_reference_20261001_v01.png` |
| Lifestyle Reference | `03-lifestyle-reference/FX-TRADER-01_lifestyle_reference_20261001_v01.png` |

## Stable Identity Block (copy exactly into every prompt)

```
Character ID: FX-TRADER-01
32 year old Middle Eastern / Mediterranean man, light olive skin, dark brown eyes,
thick dark brown hair with subtle side part, short well-groomed dark beard and mustache,
natural eyebrows, straight medium nose, defined natural jawline, realistic facial asymmetry,
realistic skin texture, approximately 180 cm, healthy moderately athletic build with broad shoulders,
same person as the provided master reference image.
```

## Identity Review Checklist (mandatory)

### Face & Head
- [ ] Same recognizable face as Master Reference
- [ ] Same approximate age
- [ ] Same hairstyle and hair color
- [ ] Same beard style and density
- [ ] Same eye color
- [ ] Same skin tone and texture quality
- [ ] Realistic facial asymmetry preserved

### Body
- [ ] Same body type and shoulder width
- [ ] Normal human proportions
- [ ] Clothing fits the same body

### Overall
- [ ] Immediately recognizable as the same person
- [ ] No “new person” feeling

**Any fail → Reject. Scene quality does not compensate for identity drift.**

## Negative Prompt Lock (baseline)

```
different person, face morph, identity drift, changed face, new face,
younger, older, different hair, different beard, different skin tone,
model-like face, perfect symmetry, beauty filter, plastic skin,
extra limbs, deformed hands, distorted proportions
```

## Trading Screens

When any monitor or phone is visible, the rules in **TRADING-SCREEN-RULES.md** are mandatory.

Order of checks:
1. Identity Lock (this file)
2. Trading Screen Accuracy (TRADING-SCREEN-RULES.md)
3. Physical Realism & Scene Logic

## Folder Rules

- `01-master-reference/` — single primary approved identity image
- `02-full-body-reference/` — full-body shots that confirm proportions
- `03-lifestyle-reference/` — natural non-portrait scenes that still lock identity
- `04-expression-sheet/` — limited approved expressions only
- `05-clothing-variants/` — approved clothing looks
- `approved-production/` — only images that passed the full checklist
- `master-reference/` — legacy

## Change Control

Changing any locked attribute requires:
1. Written reason in this file or BRAND-VISUAL-IDENTITY.md
2. New Master Reference version
3. Explicit project decision
4. Version bump and date

Do not casually regenerate the identity.
