---
name: scene
description: Generate a video prompt for a scene using defined characters and sets, optimized for the configured platform
argument-hint: "[scene description or scene number from story]"
allowed-tools:
  - Read
  - Write
  - Edit
  - AskUserQuestion
---

# Generate Scene Prompt

Create an optimized video generation prompt for Veo or Sora using the movie's established style, characters, and sets. Each scene prompt generates a single 4-12 second clip.

## Prerequisites

Read the following to inform prompt generation:
1. `.video-os/movie.md` - Get platform, style, and settings
2. `.video-os/characters/` - Load relevant character definitions
3. `.video-os/sets/` - Load relevant set definitions
4. `.video-os/scenes/` - Check for existing scenes and timeline

If movie.md doesn't exist, suggest running `/video-os:new-movie` first.

## Workflow

### Step 1: Understand the Scene

If a scene description is provided, use it. Otherwise, ask:
- What happens in this scene?
- Which characters appear?
- What location/set is it in?
- What is the emotional beat?
- Where does this fit in the story timeline?

### Step 2: Load Context

Read the relevant files:
- Movie style and platform settings
- Character descriptions for anyone appearing
- Set description for the location
- Previous scenes for continuity

### Step 3: Determine Platform

Check movie settings for platform:
- **Veo**: Use 5-part formula, include audio direction
- **Sora**: Use storyboard structure, focus on visual precision
- **Both**: Generate prompts for each platform

### Step 4: Generate Prompt

**For Veo** (use `veo-prompting` skill patterns):

```
[Cinematography from movie defaults], [character description from file],
[action in this scene], [set description from file].
[Lighting and atmosphere from movie style].
[Movie color palette and aesthetic].

[Dialogue if applicable: "Quoted speech in character voice."]

Ambient: [ambient sounds for this location]
SFX: [specific sound effects for actions]
```

**For Sora** (use `sora-prompting` skill patterns):

```
[Scene description with specific visual details from character/set files]

Cinematography: [shot type], [camera movement from movie defaults], [lens]
Light: [lighting from movie style, specific to this scene's time]
Palette: [movie color palette]

Actions: [timed action beats - count in seconds]
At second [X], [action 1].
At second [Y], [action 2].

Style: [movie aesthetic keywords]
Audio cue: [rhythm guidance even though silent]
```

### Step 5: Specify Reference Images

List which reference images should be included:

```
## Reference Images for This Scene

**Characters:**
- [Character Name]: Use [specific variant] reference image
  - Path: [path to image if available]

**Set:**
- [Set Name]: Use [specific angle/lighting] reference image
  - Path: [path to image if available]
```

For Veo: These go into "Ingredients to Video"
For Sora: Use as `input_reference` for first frame

### Step 6: Present and Confirm

Show the complete prompt and ask:
- Does this capture the scene correctly?
- Any adjustments needed?
- Ready to try this prompt?

### Step 7: Save Scene

Create `.video-os/scenes/scene-[number]-[name].md`:

```markdown
# Scene [Number]: [Title]

## Story Context

- **Timeline Position**: [where in story]
- **Previous Scene**: [what came before]
- **Purpose**: [why this scene matters]

## Scene Details

- **Location**: [Set name]
- **Characters**: [Who appears]
- **Duration**: [Target clip length]
- **Platform**: [Veo/Sora/Both]

## Veo Prompt

```
[complete Veo prompt]
```

## Sora Prompt

```
[complete Sora prompt if applicable]
```

## Reference Images

### Characters
- [Character]: [variant] - [path]

### Set
- [Set]: [variant] - [path]

## Generation Log

### Attempt 1
- **Date**: [date]
- **Result**: [pending/success/needs adjustment]
- **Notes**: [observations]

## Feedback

[To be filled after generation - use /video-os:review]
```

### Step 8: Next Steps

Inform the user:
- Copy the prompt to Veo/Sora
- Include the specified reference images
- After generation, use `/video-os:review` to record feedback and iterate

## Prompt Construction Guidelines

### Cinematography
- Use movie's default camera style unless scene requires different
- Match shot type to emotional beat (close-up for intimacy, wide for context)
- Consider continuity with adjacent scenes

### Character Appearance
- Pull exact descriptions from character files
- Include costume details
- Note any scene-specific variations (wet from rain, disheveled, etc.)

### Set Integration
- Reference set's established features
- Specify which area of the set is visible
- Include atmosphere appropriate to time/weather

### Action Timing
- One clear action per clip
- Time in beats or seconds
- Keep within platform duration limits

### Style Consistency
- Always include movie's visual style keywords
- Maintain color palette
- Match lighting to established aesthetic
