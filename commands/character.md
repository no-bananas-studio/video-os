---
name: character
description: Create or edit a character with image generation prompts for consistent reference images across all scenes
argument-hint: "[character name or description]"
allowed-tools:
  - Read
  - Write
  - Edit
  - Bash
  - AskUserQuestion
---

# Create or Edit Character

Build a character definition with prompts for generating consistent reference images. These reference images will be fed into Veo or Sora to maintain character consistency across all clips.

## Prerequisites

Ensure `.video-os/` directory exists. If not, suggest running `/video-os:new-movie` first.

Create `.video-os/characters/` directory if it doesn't exist.

## Workflow

### Step 1: Gather Character Details

If a description is provided, expand upon it. Otherwise, ask about:

**Identity:**
- Name or identifier
- Age range
- Role in the story

**Physical Appearance:**
- Build and height
- Skin tone and complexion
- Hair (color, style, length)
- Distinguishing features (scars, freckles, etc.)

**Costume/Wardrobe:**
- Primary outfit for this story
- Colors and materials
- Accessories
- Alternate outfits if needed

**Character Essence:**
- Personality traits that show visually
- Typical posture and body language
- Emotional default (weary, alert, nervous, confident)

### Step 2: Create Initial Image Prompt

Generate an image generation prompt for creating the character reference:

```
Portrait of [character description], [age], [physical features].
[Hair description]. [Skin/complexion]. [Distinguishing features].
Wearing [outfit description]. [Accessories].
[Pose/expression]. [Lighting consistent with movie style].
[Style keywords from movie settings].
```

**Example:**
```
Portrait of a weary private detective, late 40s, weathered face with
deep-set eyes and stubble. Silver-gray hair swept back, receding at
temples. Tanned, lined skin. Small scar above left eyebrow.
Wearing rumpled brown suit, loosened tie, coffee-stained shirt.
Fedora in hand. Expression of tired skepticism.
Soft side lighting, film noir aesthetic, 1940s period.
```

### Step 3: Iteration Loop

Present the prompt and ask:
- Does this capture the character correctly?
- Any adjustments to features, clothing, or style?
- Ready to generate, or need refinement?

Iterate until the user confirms the description is accurate.

### Step 4: Generate Reference Image Variants

Once the primary description is confirmed, create prompts for reference image variants:

**Front Portrait:**
```
[Character description], front-facing portrait, neutral expression,
studio lighting, clean background, [style keywords].
```

**Three-Quarter View:**
```
[Character description], three-quarter angle, slight turn to left,
[signature expression], [style keywords].
```

**Side Profile:**
```
[Character description], side profile facing right, [style keywords].
```

**Full Body:**
```
Full body shot of [character description], standing naturally,
[outfit visible head to toe], [style keywords].
```

**Action/Emotion Variants:**
```
[Character description], [specific emotion/action], [style keywords].
```
- Happy/smiling
- Angry/intense
- Sad/contemplative
- In motion (walking, running)

**Alternate Outfits (if applicable):**
```
[Character description], wearing [alternate outfit], [style keywords].
```

### Step 5: Save Character File

Create `.video-os/characters/[character-name].md`:

```markdown
# [Character Name]

## Overview

- **Role**: [role in story]
- **Age**: [age range]
- **Build**: [physical build]

## Appearance

[Detailed physical description]

## Wardrobe

### Primary Outfit
[Primary outfit description]

### Alternate Outfits
[If applicable]

## Reference Image Prompts

### Primary Portrait
```
[prompt]
```

### Front Portrait
```
[prompt]
```

### Three-Quarter View
```
[prompt]
```

### Side Profile
```
[prompt]
```

### Full Body
```
[prompt]
```

### Expressions/Actions
```
[emotion 1 prompt]
```
```
[emotion 2 prompt]
```

## Notes

[Any additional notes about portraying this character]

## Generated Images

[User will add paths/links to generated reference images here]
```

### Step 6: Next Steps

Inform the user:
- Use these prompts with your preferred image generator (Midjourney, DALL-E, etc.)
- Once you have reference images you're happy with, add the file paths to the character file
- These images will be used as references when generating scene prompts

## Tips

- Emphasize features that need to be consistent across scenes
- Include the movie's visual style in all prompts for coherence
- Suggest 3-5 core reference images minimum per character
- For Veo: reference images feed into "Ingredients to Video"
- For Sora: reference images can be used as first-frame anchors
- Keep descriptions specific enough to regenerate if needed
