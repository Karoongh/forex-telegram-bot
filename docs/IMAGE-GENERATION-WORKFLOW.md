# Image Generation Workflow — FX-TRADER-01

> Operational workflow for creating consistent, realistic images of the recurring fictional trader character used by the Forex project.
>
> This document works together with `docs/BRAND-VISUAL-IDENTITY.md`. The Brand Visual Identity document defines **what FX-TRADER-01 is**; this document defines **how to generate, review, store, and hand off images**.

## 1. Purpose

The project uses a recurring fictional trader character for brand, educational, lifestyle, social-media, and trading-related visual content.

The objective is long-term visual consistency across different scenes and image-generation tools.

The system must preserve the character's identity while allowing the following to change:

- Location
- Activity
- Body language
- Camera angle
- Composition
- Time of day
- Clothing
- Environment
- Content category

The workflow is designed so that another team member can continue image production without relying on undocumented personal knowledge.

---

## 2. Source of Truth

There are two levels of documentation:

### Primary identity specification

`docs/BRAND-VISUAL-IDENTITY.md`

This is the authoritative source for:

- Character appearance
- Character ID
- Personality
- Lifestyle direction
- Clothing
- Natural behavior
- Photography style
- Lighting
- Shadow realism
- Skin and physical realism
- Environment
- Composition
- Master Prompt
- Negative Prompt

### Operational workflow

This document, `docs/IMAGE-GENERATION-WORKFLOW.md`, is authoritative for:

- How to prepare prompts
- How to use reference images
- How to vary scenes
- How to review generations
- How to reject/regenerate images
- How to name and organize assets
- How to work with different image tools
- How to hand the process to another team member

If a prompt conflicts with the Brand Visual Identity document, the Brand Visual Identity document takes priority unless the project explicitly changes it.

---

## 3. Character ID

Always identify the recurring character internally as:

```
FX-TRADER-01
```

Do not create a new physical identity for each post.

The goal is:

```
ONE CHARACTER
    +
MANY REALISTIC SCENES
```

not:

```
ONE NEW CHARACTER
    +
ONE NEW IMAGE
```

---

## 4. The Two-Layer Prompt System

Do not rewrite the entire character specification from scratch for every image.

Every image prompt should be treated as two layers.

### Layer A — Stable Identity

This information should remain substantially unchanged:

- FX-TRADER-01
- Fictional male
- Approximately 32 years old
- Middle Eastern / Mediterranean appearance
- Light olive skin
- Dark brown eyes
- Thick dark brown hair
- Subtle side part
- Short well-groomed dark beard and mustache
- Natural eyebrows
- Straight medium-sized nose
- Defined but natural jawline
- Realistic facial asymmetry
- Realistic skin texture
- Approximately 180 cm
- Healthy moderately athletic build
- Naturally broad shoulders
- Realistic human proportions
- Intelligent, disciplined, calm, experienced and approachable presence
- Successful professional, not a fashion model or fitness influencer
- No get-rich-quick-guru appearance

Also preserve:

- Photorealistic real-world photography
- Natural human behavior
- Natural lighting
- Physically consistent shadows
- Realistic skin and hair
- Believable environments
- No excessive luxury signaling

### Layer B — Variable Scene

This is the part that changes for each image:

- SCENE
- LOCATION
- ACTIVITY
- TIME
- BODY LANGUAGE
- CLOTHING
- CAMERA
- LIGHT
- MOOD
- COMPOSITION
- OPTIONAL PROPS

Only the variable scene should normally change between generations.

---

## 5. Standard Scene Brief

Before generating an image, complete this brief:

```
CHARACTER:
FX-TRADER-01

CONTENT CATEGORY:
[Trading / Technical / Educational / Lifestyle / Community / Brand]

SCENE:
[What is happening?]

LOCATION:
[Where is it happening?]

ACTIVITY:
[What is the character doing?]

TIME:
[Morning / Afternoon / Evening / Night / Unspecified]

BODY LANGUAGE:
[Relaxed / Focused / Walking / Reading / Working / etc.]

CLOTHING:
[Specific outfit]

CAMERA:
[Wide / Medium / Close / Over-the-shoulder / Side profile / etc.]

CAMERA ANGLE:
[Front / Side / Three-quarter / Behind / Elevated / etc.]

LIGHT:
[Natural window light / cloudy daylight / practical lamp / etc.]

SHADOWS:
[Describe the physically plausible shadow direction when relevant.]

MOOD:
[Calm / focused / relaxed / professional / etc.]

COMPOSITION:
[Centered / environmental / off-center / negative space / etc.]

PROPS:
[Laptop / phone / coffee / notebook / charts / etc.]

TEXT OR BRANDING:
[Usually none unless explicitly required]
```

This brief is prepared before the final image-generation prompt.

---

## 6. Master Prompt Construction

The final prompt should combine:

```
STABLE IDENTITY
+
REFERENCE IMAGE INSTRUCTION
+
SCENE BRIEF
+
PHOTOGRAPHY RULES
+
LIGHTING/SHADOW RULES
+
REALISM REQUIREMENTS
+
NEGATIVE PROMPT
```

A practical structure is:

```
Create a photorealistic real-world photograph of FX-TRADER-01.

[Stable identity summary]

Use the supplied character reference image as the primary identity reference.
Preserve the same recognizable face, approximate age, hairstyle, beard,
skin tone, eye color and body proportions.

SCENE:
[Scene brief]

PHOTOGRAPHY:
[Camera/composition]

LIGHTING:
[Natural light description]

SHADOWS:
[Physically consistent shadows]

REALISM:
[Natural skin, hair, anatomy, environment and photographic imperfections]

Avoid:
[Negative prompt]
```

---

## 7. Reference Image Is More Important Than Prompt Repetition

Once the Master Character Reference is approved, it should become the primary visual identity anchor.

The workflow is:

```
MASTER CHARACTER REFERENCE
          ↓
     NEW SCENE PROMPT
          ↓
     IMAGE GENERATION
          ↓
   IDENTITY CHECK
          ↓
     APPROVE / REJECT
```

When an image tool supports any of the following, use them where appropriate:

- Character reference
- Reference image
- Image-to-image
- Identity conditioning
- Seed
- Character consistency feature
- LoRA or equivalent identity model

Do not assume that the same text prompt alone will produce the same person across different tools.

---

## 8. Creating the Master Character Reference

This is the first image-generation milestone.

### Target

Create a neutral, high-quality reference image that makes the character easy to identify.

### Recommended first reference

- FX-TRADER-01
- Upper-body or three-quarter portrait
- Clear face
- Neutral natural expression
- Simple realistic clothing
- No visible logos
- Simple non-distracting environment
- Natural light
- Realistic skin texture
- No dramatic cinematic effects
- No luxury objects
- No trading-profit claims
- No text overlay

The reference should prioritize identity accuracy over artistic complexity.

### Second reference

After the primary reference is approved, create a full-body reference to establish:

- Height impression
- Body proportions
- Shoulder width
- Clothing fit
- General posture

### Third reference

Create one natural lifestyle reference, such as:

- Sitting on a sofa with a laptop
- Working naturally at a desk
- Looking at the screen instead of the camera

This tests whether the character remains consistent outside a portrait.

---

## 9. Daily Image Budget Strategy

When image-generation capacity is limited, every generation should have a defined purpose.

For a daily budget of approximately 2–3 images:

### Phase 1 — Character setup

Use the first generation for the Master Character Reference.

Use subsequent generations only to fix important identity problems or establish additional reference views.

### Phase 2 — Production

Once the reference is approved:

- Prefer one planned generation per content idea.
- Use another generation for a meaningful alternative only when necessary.
- Reserve the final generation for a correction or high-priority asset when possible.

Do not spend the daily budget on many slightly different prompts without a review objective.

### Rule

Every generation should answer one of these questions:

1. Is the character identity correct?
2. Is the intended scene correct?
3. Is the realism correct?
4. Is the composition suitable?
5. Is this the approved production asset?

---

## 10. Tool-Agnostic Workflow

The exact interface differs between ChatGPT and other image tools, but the underlying workflow remains the same.

### Step 1 — Read the identity specification

Review:

```
docs/BRAND-VISUAL-IDENTITY.md
```

### Step 2 — Load the approved character reference

Use the current approved FX-TRADER-01 reference.

### Step 3 — Define the scene

Complete the Standard Scene Brief.

### Step 4 — Build the prompt

Combine stable identity + reference instruction + variable scene.

### Step 5 — Add tool-specific controls

Depending on the tool, configure:

- Reference-image strength
- Character-reference strength
- Image-to-image strength
- Aspect ratio
- Seed
- Style strength
- Negative prompt
- Resolution

Do not change the identity specification merely because a tool uses different parameter names.

### Step 6 — Generate

Generate the smallest useful number of candidates.

### Step 7 — Review

Use the checklist in Section 12.

### Step 8 — Approve or reject

Never keep an image simply because the scene looks good if the character identity has drifted.

### Step 9 — Archive

Save the approved image using the naming rules in Section 14.

### Step 10 — Record important changes

If a new reference image becomes the official master, update the project asset record and tell the team.

---

## 11. Tool-Specific Translation Rules

The project should remain tool-independent.

When moving the workflow to another tool:

### If the tool supports reference images

Use the approved FX-TRADER-01 image as the character reference.

### If the tool supports character references

Use the strongest practical character-reference setting that preserves identity without destroying the requested scene.

### If the tool supports negative prompts

Use the project's Negative Prompt from the Brand Visual Identity document, then add only scene-specific exclusions.

### If the tool supports seeds

Record the seed when useful for reproducibility.

A seed is not a replacement for the character reference.

### If the tool supports image-to-image

Use it carefully. The objective is identity consistency, not copying the previous composition.

### If the tool supports LoRA or identity training

A future project may create a dedicated identity model, but this should not be treated as necessary for the initial workflow.

### If the tool does not support reference images

Use the Stable Identity layer in the prompt and expect lower identity consistency. Prefer tools that support visual identity references for production work.

---

## 12. Image Review Checklist

Every candidate must be reviewed before approval.

### A. Identity

Check:

- Same recognizable face
- Same approximate age
- Same hairstyle
- Same beard
- Same skin tone
- Same eye color
- Same facial proportions
- Same general body proportions

Reject if the character looks like a different person.

### B. Anatomy

Check:

- Hands
- Fingers
- Arms
- Legs
- Shoulders
- Neck
- Face
- Ears
- Teeth
- Reflections

Reject obvious anatomical errors.

### C. Skin and hair

Check:

- Natural pores
- Realistic beard
- Individual hair texture
- No plastic skin
- No excessive beauty retouching
- No unnatural facial symmetry

### D. Lighting

Check:

- Light direction makes sense
- Highlights match the light source
- Face lighting is plausible
- Background lighting is plausible
- No unexplained bright areas

### E. Shadows

This is a critical review.

Check:

- Object shadows have a plausible direction
- Contact shadows exist where appropriate
- Furniture touches the floor correctly
- Face/body shadows match the light
- No duplicated shadows
- No contradictory light sources
- No floating objects caused by missing shadows

### F. Environment

Check:

- Objects have realistic scale
- Furniture is physically plausible
- Reflections make sense
- Perspective is coherent
- The environment looks lived-in
- No accidental luxury signaling

### G. Photography

Check:

- Natural perspective
- Realistic depth of field
- Believable lens behavior
- Natural framing
- No excessive HDR
- No artificial commercial look

### H. Brand behavior

Check:

- Character appears professional
- Character does not look like a get-rich-quick guru
- No unrealistic wealth signaling
- No implied guaranteed profit
- No fake performance evidence

---

## 13. Reject / Regenerate Rules

Reject the image if any major issue appears in:

- Identity
- Anatomy
- Hands
- Facial structure
- Lighting
- Shadows
- Perspective
- Unrealistic environment
- Excessive retouching
- Brand-inconsistent wealth signaling
- Text or logos that were not requested

Minor imperfections that make the photograph feel real are acceptable.

Do not regenerate merely because an image is not technically perfect.

The goal is:

```
REALISTIC + CONSISTENT + USEFUL
```

not:

```
PERFECT + ARTIFICIAL
```

---

## 14. Asset Naming and Storage

Use a predictable naming convention.

Recommended structure (current):

```
assets/
└── character/
    └── FX-TRADER-01/
        ├── 00-identity-lock/
        ├── 01-master-reference/
        ├── 02-full-body-reference/
        ├── 03-lifestyle-reference/
        ├── 04-expression-sheet/
        ├── 05-clothing-variants/
        ├── approved-production/
        └── master-reference/   # legacy
```

Recommended filename:

```
FX-TRADER-01_<category>_<scene>_<YYYYMMDD>_v01
```

Examples:

```
FX-TRADER-01_master_reference_20260927_v01
FX-TRADER-01_lifestyle_sofa_laptop_20260928_v01
FX-TRADER-01_trading_desk_analysis_20260929_v01
FX-TRADER-01_educational_cafe_20260930_v01
```

Use lowercase or the project's established naming convention consistently once the asset system is implemented.

---

## 15. Master Reference Management

There should be one clearly identified official master reference.

Recommended record:

```
Character ID: FX-TRADER-01
Master Reference: [approved asset path]
Status: APPROVED
Created: [date]
Last Reviewed: [date]
```

Do not silently replace the master reference.

If a better reference is created:

1. Compare it with the existing master.
2. Confirm that identity has not changed.
3. Mark the new image as a candidate.
4. Explicitly approve it as the new master.
5. Update the documentation/asset record.
6. Preserve the previous master in the archive.

---

## 16. Scene Categories

The same character can be used across four broad content groups.

### Trading / Technical

Examples:

- Reviewing forex charts
- Sitting at a trading desk
- Checking market data
- Writing trading notes
- Preparing before a trading session

### Educational

Examples:

- Explaining a chart
- Reading a financial book
- Recording educational content
- Taking notes
- Teaching from a laptop

### Lifestyle

Examples:

- Coffee at home
- Sofa and laptop
- Balcony work
- City walk
- Café
- Reading
- End-of-day relaxation

### Community / Brand

Examples:

- Recording a message
- Preparing a community post
- Talking to a camera
- Working in a coworking space
- Casual professional portrait

Avoid making every image a trading-desk image. The character should feel like a real person with a professional life.

---

## 17. Prompt Variation Rules

Change:

- Scene
- Location
- Activity
- Camera
- Composition
- Time
- Clothing
- Body language

Preserve:

- Identity
- Approximate age
- Facial structure
- Hair
- Beard
- Skin tone
- Eye color
- Body proportions
- Overall realism
- Natural lighting philosophy
- Physical shadow logic
- Professional-but-relatable lifestyle

This creates visual variety without character drift.

---

## 18. Example Production Prompt

The following is an example of how a scene should be assembled.

```
Create a photorealistic real-world photograph of FX-TRADER-01 using the supplied
approved character reference as the primary identity reference.

Preserve the same recognizable face, approximate age, dark brown eyes, thick
dark brown hair with subtle side part, short well-groomed dark beard and
mustache, light olive skin, natural facial asymmetry and realistic body
proportions.

SCENE:
FX-TRADER-01 is sitting comfortably on a sofa with his legs naturally
stretched out while reviewing forex charts on a laptop.

LOCATION:
A believable modern apartment living room with a lived-in professional
atmosphere, books, coffee and a few natural personal objects.

BODY LANGUAGE:
Relaxed posture, slightly leaning back, focused on the laptop. He is not
looking at the camera. The moment should feel candid rather than posed.

CLOTHING:
Dark charcoal crew-neck shirt and dark casual trousers.

CAMERA:
Candid medium-wide photograph from a slightly side angle, approximately
35mm-equivalent perspective, natural depth of field.

LIGHT:
Natural morning window light entering from the left side of the room, mixed
with subtle ordinary ambient room light.

SHADOWS:
All shadows must be physically consistent with the window and room lights,
including realistic contact shadows beneath the sofa and natural shadows on
the character and surrounding objects.

REALISM:
Natural skin pores, beard texture, individual hair strands, realistic fabric
wrinkles, believable furniture scale, natural perspective, subtle photographic
imperfections and realistic depth of field.

The photograph should feel like an authentic moment from the daily life of a
professional trader, not a commercial advertisement.

Avoid plastic skin, excessive retouching, fashion-model styling, luxury
wealth signaling, supercars, private jets, cash, champagne, casino imagery,
fake profit claims, dramatic studio lighting, artificial rim lighting,
perfectly symmetrical posing, contradictory shadows, duplicate shadows,
floating objects, distorted hands, extra fingers, malformed anatomy,
unrealistic reflections, excessive HDR and AI-generated facial artifacts.
```

---

## 19. Prompt Shortening for Tools With Small Input Limits

If an image tool has a limited prompt length, prioritize in this order:

1. Character identity
2. Reference-image instruction
3. Scene
4. Camera/composition
5. Natural lighting
6. Shadow realism
7. Photorealism
8. Key negative constraints

Do not remove identity information before removing decorative prose.

A short prompt should still preserve the identity anchor.

---

## 20. ChatGPT Production Workflow

When generating with ChatGPT:

1. Use the approved FX-TRADER-01 reference image when available.
2. Use the stable identity specification from the GitHub documentation.
3. Prefer the two-layer approach (stable identity + variable scene).
4. Review every candidate against the Identity Checklist.
5. Reject identity drift even if the scene is attractive.

---

## 21. Common Failure Modes and Fixes

### Failure: Face changes between images

Cause:
- Text-only prompting without a strong reference image
- Weak reference strength
- Rewriting the identity description from scratch

Fix:
- Always load the Master Reference
- Keep the Stable Identity block fixed
- Increase character-reference strength if the tool allows

### Failure: Body proportions drift

Cause:
- Missing full-body reference
- Scene-driven generation that prioritizes composition over identity

Fix:
- Use the approved Full-body Reference when body is visible
- Explicitly require the same body proportions in the prompt

### Failure: Plastic / model look

Cause:
- Beauty-filter language or high aesthetic strength
- Missing realism constraints

Fix:
- Emphasize natural skin, pores, asymmetry and photographic imperfections

### Failure: Luxury or get-rich-quick signaling

Cause:
- Props or environments that imply unrealistic wealth

Fix:
- Keep environments professional and lived-in
- Avoid supercars, private jets, cash, champagne, etc.

### Failure: Posed advertisement look

Cause:
- Direct camera stare
- Perfect posture
- Centered composition
- Artificial smile

Fix:
- Use candid behavior, environmental compositions and varied camera angles.

### Failure: Scene is good but person is wrong

Fix:
- Reject the image. Scene quality does not compensate for identity drift.

---

## 22. Brand Credibility and Compliance

The fictional character is a visual asset, not evidence of trading performance.

Images must not be used to imply:

- Guaranteed profit
- Guaranteed success
- Zero risk
- Verified personal trading results
- Real wealth that has not been documented
- Testimonials that did not occur
- A real person's identity when none exists

Actual financial claims should be supported separately by appropriate documentation, disclosures and factual evidence.

The character should remain clearly fictional within the project's internal asset system.

---

## 23. Brand Credibility and Compliance

(See section above — retained for continuity.)

---

## 24. Change-Control Rules

Changes to the character identity must be intentional.

Do not casually modify:

- Age
- Face
- Hair
- Beard
- Skin tone
- Eye color
- Body type
- Core personality
- Overall lifestyle direction

If a change is needed:

1. Document the reason.
2. Update `BRAND-VISUAL-IDENTITY.md`.
3. Decide whether the master reference must be replaced.
4. Re-evaluate existing approved images if the change is significant.
5. Record the date and change.

---

## 25. Current Implementation Status

Current status (updated 2026-10-02):

```
DOCUMENTATION: READY
CHARACTER SPECIFICATION: DEFINED
GENERATION WORKFLOW: DEFINED
MASTER CHARACTER REFERENCE: APPROVED AND LOCKED
FULL-BODY REFERENCE: APPROVED
LIFESTYLE REFERENCE: APPROVED
IDENTITY LOCK: OFFICIALLY ACTIVE
PRODUCTION ASSET LIBRARY: READY TO START
```

### Approved reference locations

- Master: `assets/character/FX-TRADER-01/01-master-reference/FX-TRADER-01_master_reference_20260928_v01.jpg`
- Full-body: `assets/character/FX-TRADER-01/02-full-body-reference/FX-TRADER-01_full_body_reference_20261001_v01.png`
- Lifestyle: `assets/character/FX-TRADER-01/03-lifestyle-reference/FX-TRADER-01_lifestyle_reference_20261001_v01.png`

### Operational lock document

`assets/character/FX-TRADER-01/00-identity-lock/CHARACTER-LOCK.md`

### Immediate next milestone

Begin production scenes under the character-identity-lock rules.

Always load the Master Reference as the primary identity anchor.
Reject any image that fails the Identity Review Checklist.

---

## 26. Quick Reference

For daily use:

```
1. READ BRAND VISUAL IDENTITY
2. LOAD FX-TRADER-01 MASTER REFERENCE
3. DEFINE SCENE
4. BUILD STABLE IDENTITY + VARIABLE SCENE PROMPT
5. GENERATE
6. CHECK IDENTITY
7. CHECK ANATOMY
8. CHECK LIGHTING
9. CHECK SHADOWS
10. CHECK REALISM
11. APPROVE OR REJECT
12. SAVE WITH STANDARD NAME
```

The most important rule is:

> Preserve the character; vary the scene.

The second most important rule is:

> A reference image is the primary identity anchor. Text prompts alone should not be treated as sufficient for long-term character consistency.
