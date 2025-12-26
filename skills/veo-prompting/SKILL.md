---
name: Veo Prompting
description: This skill should be used when the user asks to "generate a Veo prompt", "create a video with Veo", "write a prompt for Google Veo", "use Veo 3", or when generating video prompts and the movie settings specify Veo as the target platform. Provides best practices for Google Veo 3 video generation prompts.
version: 0.1.0
---

# Veo 3 Prompting Guide

This skill provides comprehensive guidance for crafting effective prompts for Google Veo 3 video generation. Veo excels at cinematic video with synchronized audio, dialogue, and sound effects.

## When to Use Veo vs Sora

Choose Veo when:
- Audio is essential (dialogue, sound effects, ambient sounds)
- Cinematic film quality is the priority
- Working with 4, 6, or 8 second clips
- Using reference images for character/set consistency ("Ingredients to Video" feature)

For silent clips or 12-second duration, consider the `sora-prompting` skill instead.

## Core Prompt Structure

Follow the **Five-Part Formula** for every Veo prompt:

```
[Cinematography] + [Subject] + [Action] + [Context] + [Style & Ambiance]
```

### Components Breakdown

1. **Cinematography**: Camera shot, movement, lens, composition
2. **Subject**: Who or what is the focus
3. **Action**: What is happening
4. **Context**: Setting, time, environment
5. **Style & Ambiance**: Mood, lighting, aesthetic, film style

### Example Application

```
Medium shot, a tired corporate worker, rubbing his temples in exhaustion,
in front of a bulky 1980s computer in a cluttered office late at night.
The scene is lit by harsh fluorescent overhead lights and the green glow
of the monochrome monitor. Retro aesthetic, shot as if on 1980s color film,
slightly grainy.
```

## Cinematography Vocabulary

### Camera Movements

| Movement | Description | Use Case |
|----------|-------------|----------|
| Dolly shot | Forward/backward movement | Approaching or retreating from subject |
| Tracking shot | Lateral camera movement | Following subject horizontally |
| Crane shot | Vertical ascending/descending | Revealing scale, establishing shots |
| Slow pan | Horizontal rotation | Scanning environments |
| POV shot | First-person perspective | Immersive, subjective scenes |
| Aerial view | Bird's eye perspective | Establishing geography |

### Composition Shots

| Shot Type | Description |
|-----------|-------------|
| Wide shot | Full scene view |
| Medium shot | Subject from waist up |
| Close-up | Face or object focus |
| Extreme close-up | Detailed focus (eyes, hands) |
| Two-shot | Two subjects in frame |
| Low angle | Camera looking up at subject |
| High angle | Camera looking down at subject |

### Lens & Focus

- **Shallow depth of field** - Blurred background, subject isolation
- **Deep focus** - All elements sharp
- **Wide-angle lens** - Expansive, slight distortion
- **Macro lens** - Extreme detail on small objects
- **Soft focus** - Dreamy, diffused look

## Audio Direction

Veo 3 generates synchronized audio. Include audio cues in prompts.

### Dialogue

Use quotation marks for specific speech with tone indicators:

```
A woman says in a weary voice, "Of all the offices in this town,
you had to walk into mine."
```

### Sound Effects (SFX)

Be specific and descriptive:

```
SFX: thunder cracks in the distance
SFX: rustle of dense leaves, distant exotic bird calls
SFX: footsteps on wet gravel
```

### Ambient Noise

Define background soundscapes:

```
Ambient noise: the quiet hum of a starship bridge
Ambient noise: bustling city traffic, distant sirens
```

## Timestamp Prompting

For precise multi-shot sequences within a single clip, use timestamp notation:

```
[00:00-00:02] Medium shot from behind explorer with leather satchel,
pushing aside jungle vine to reveal hidden path.

[00:02-00:04] Reverse shot of explorer's freckled face, expression
filled with awe gazing upon ancient, moss-covered ruins.
SFX: rustle of dense leaves, distant exotic bird calls.

[00:04-00:06] Tracking shot following explorer running hand over
intricate carvings on crumbling stone wall. Emotion: Wonder and reverence.
```

## Reference Image Workflows

### Ingredients to Video

To maintain character and set consistency across clips:

1. Generate reference images for characters and sets using an image generator
2. Use Veo's "Ingredients to Video" feature with these references
3. Reference the images in the prompt:

```
Using the provided images for the detective, the woman, and the office
setting, create a medium shot of the detective behind his desk.
```

### First & Last Frame

For smooth transitions:

1. Generate starting frame image
2. Generate ending frame image
3. Use "First and Last Frame" feature to animate between them

## Technical Specifications

| Parameter | Options |
|-----------|---------|
| Resolution | 720p, 1080p |
| Aspect Ratio | 16:9 (landscape), 9:16 (portrait) |
| Duration | 4, 6, or 8 seconds |
| Audio | Dialogue, SFX, ambient (synchronized) |

## Negative Prompting

Specify exclusions using descriptive language, not simple negatives:

**Good**: "a desolate landscape with no buildings or roads visible"
**Avoid**: "no man-made structures"

## Style Keywords Reference

For detailed lists of lighting, mood, and aesthetic keywords, see:
- **`references/style-keywords.md`** - Complete vocabulary for visual styles
- **`references/camera-vocabulary.md`** - Extended cinematography terms

## Example Prompts

Working examples for common scenarios in:
- **`examples/dialogue-scene.md`** - Character conversation
- **`examples/action-sequence.md`** - Dynamic movement
- **`examples/establishing-shot.md`** - Location reveals

## Best Practices Summary

1. Always use the five-part formula for structure
2. Be specific about camera movements and framing
3. Describe lighting explicitly
4. Include dialogue in quotation marks with tone
5. Layer ambient sounds with specific SFX
6. Use timestamp prompting for multi-shot sequences
7. Reference character/set images for consistency
8. Use descriptive exclusions rather than simple negatives
