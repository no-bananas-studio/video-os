---
name: new-movie
description: Initialize a new AI movie project with visual style, platform settings, and creative direction
argument-hint: "[movie name or concept]"
allowed-tools:
  - Read
  - Write
  - Bash
  - AskUserQuestion
---

# Initialize New Movie Project

Create a new AI movie project by establishing the visual foundation and technical settings. This command sets up the project structure and captures the creative vision that will guide all subsequent scene generation.

## Workflow

### Step 1: Create Project Structure

Create the `.video-os/` directory in the current project folder:

```
.video-os/
├── movie.md          # Style, settings, story
├── characters/       # Character definitions
├── sets/             # Set/location definitions
└── scenes/           # Scene prompts and feedback
```

### Step 2: Gather Movie Settings

Ask the user about each setting, providing recommendations based on their concept:

**Platform Selection:**
- Veo - Best for dialogue, sound effects, audio-driven scenes (4/6/8 sec)
- Sora - Best for visual precision, longer clips, no audio needed (4/8/12 sec)
- Both - Generate prompts for both platforms

**Visual Style:**
- Overall aesthetic (cinematic, documentary, animation, etc.)
- Film era reference (modern digital, 35mm film grain, 16mm, etc.)
- Mood and tone (dark, light, warm, cool, melancholic, energetic)

**Color:**
- Full color with palette preference
- Black and white
- Desaturated/muted
- Stylized (neon, sepia, etc.)

**Aspect Ratio:**
- 16:9 (landscape, standard widescreen)
- 9:16 (portrait, vertical video)

**Default Clip Duration:**
- Veo: 4, 6, or 8 seconds
- Sora: 4, 8, or 12 seconds

**Default Camera Style:**
- Smooth/steady (tripod, dolly, Steadicam)
- Handheld (documentary, intimate, urgent)
- Static (locked off, contemplative)
- Dynamic (crane, drone, tracking)

### Step 3: Save Configuration

Write all settings to `.video-os/movie.md` with this structure:

```markdown
# [Movie Title]

## Settings

- **Platform**: [Veo/Sora/Both]
- **Aspect Ratio**: [16:9/9:16]
- **Default Duration**: [X seconds]
- **Default Camera**: [style]

## Visual Style

[Detailed description of the overall visual aesthetic]

## Color Palette

[Color approach and specific palette if applicable]

## Mood & Tone

[Emotional quality, atmosphere, genre feel]

## Story

[To be developed with /video-os:story]

## Notes

[Any additional creative direction or references]
```

### Step 4: Confirm Setup

Display a summary of the project configuration and next steps:
- Use `/video-os:story` to develop the narrative
- Use `/video-os:character` to create characters
- Use `/video-os:set` to create sets/locations
- Use `/video-os:scene` to generate scene prompts

## Tips

- If user provides a concept, infer reasonable defaults and confirm
- Reference the `veo-prompting` or `sora-prompting` skills for platform guidance
- Encourage specific visual references (films, directors, photographers)
- Store all decisions for consistency across scenes
