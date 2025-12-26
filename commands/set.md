---
name: set
description: Create or edit a set/location with image generation prompts for consistent reference images across all scenes
argument-hint: "[set name or description]"
allowed-tools:
  - Read
  - Write
  - Edit
  - Bash
  - AskUserQuestion
---

# Create or Edit Set/Location

Build a set or location definition with prompts for generating consistent reference images. These reference images will be fed into Veo or Sora to maintain location consistency across all clips filmed in this setting.

## Prerequisites

Ensure `.video-os/` directory exists. If not, suggest running `/video-os:new-movie` first.

Create `.video-os/sets/` directory if it doesn't exist.

## Workflow

### Step 1: Gather Set Details

If a description is provided, expand upon it. Otherwise, ask about:

**Location Type:**
- Interior or exterior
- Name or identifier
- Real-world reference or fictional
- Time period

**Spatial Description:**
- Size and layout
- Key architectural features
- Focal points and landmarks
- Exits and entrances

**Atmosphere:**
- Lighting conditions (time of day, light sources)
- Weather (if exterior)
- Sound environment (for Veo prompts)
- Mood and feeling

**Details and Props:**
- Furniture or key objects
- Materials and textures
- Colors and palette
- State of repair (pristine, worn, abandoned)

### Step 2: Create Initial Image Prompt

Generate an image generation prompt for creating the set reference:

```
[Interior/Exterior] of [location type], [time period/style].
[Architectural description]. [Key features].
[Furniture/objects]. [Materials and textures].
[Lighting conditions]. [Atmosphere/mood].
[Color palette]. [Style keywords from movie settings].
Empty of people, establishing shot composition.
```

**Example:**
```
Interior of 1950s American diner, chrome and formica aesthetic.
Long counter with red vinyl spinning stools, checkered floor tiles.
Booths with red vinyl upholstery along windows. Vintage jukebox in corner.
Neon signs, coffee machines, pie display case.
Early morning light through windows, warm and nostalgic.
Cherry red, cream white, chrome silver palette.
Kodachrome color, slightly desaturated period feel.
Empty of people, wide establishing composition.
```

### Step 3: Iteration Loop

Present the prompt and ask:
- Does this capture the location correctly?
- Any adjustments to layout, details, or atmosphere?
- Ready to generate, or need refinement?

Iterate until the user confirms the description is accurate.

### Step 4: Generate Reference Image Variants

Once the primary description is confirmed, create prompts for reference image variants:

**Wide Establishing:**
```
Wide establishing shot, [set description], showing full layout,
[lighting], [style keywords]. No people.
```

**Medium Interior/Detail:**
```
Medium shot, [specific area of set], [key details visible],
[lighting], [style keywords]. No people.
```

**Specific Angles:**
```
[Set description], view from [specific angle/position],
[what's visible], [style keywords]. No people.
```
- From entrance looking in
- From back looking toward entrance
- Corner perspective
- Close-up of key feature

**Time/Lighting Variants:**
```
[Set description], [different time of day/lighting condition],
[how atmosphere changes], [style keywords]. No people.
```
- Morning light
- Afternoon
- Evening/night
- Specific weather (rain, fog, etc.)

**Detail Shots:**
```
Close-up of [specific object/feature in set],
[surrounding context], [style keywords].
```

### Step 5: Save Set File

Create `.video-os/sets/[set-name].md`:

```markdown
# [Set Name]

## Overview

- **Type**: [Interior/Exterior]
- **Location**: [What kind of place]
- **Period**: [Time period]
- **Story Role**: [How it's used in the story]

## Description

[Detailed description of the location]

## Key Features

- [Feature 1]
- [Feature 2]
- [Feature 3]

## Atmosphere

- **Lighting**: [Typical lighting conditions]
- **Sound**: [Ambient sounds for Veo]
- **Mood**: [Emotional quality]

## Color Palette

[Colors that define this space]

## Reference Image Prompts

### Wide Establishing
```
[prompt]
```

### Medium Detail
```
[prompt]
```

### Entrance View
```
[prompt]
```

### Key Feature Close-Up
```
[prompt]
```

### Alternate Lighting/Time
```
[prompt for different conditions]
```

## Notes

[Any additional notes about filming in this location]

## Generated Images

[User will add paths/links to generated reference images here]
```

### Step 6: Next Steps

Inform the user:
- Use these prompts with your preferred image generator
- Generate multiple angles and lighting conditions for flexibility
- Add file paths to generated images in the set file
- These will be referenced when generating scene prompts

## Tips

- Emphasize distinctive features that identify this location
- Match lighting to the movie's overall visual style
- Include the movie's color palette in all prompts
- For Veo: reference images feed into "Ingredients to Video"
- For Sora: use as first-frame anchors for establishing shots
- Generate empty set images (no people) for maximum flexibility
- Consider which areas of the set different scenes will use
