---
name: Sora Prompting
description: This skill should be used when the user asks to "generate a Sora prompt", "create a video with Sora", "write a prompt for OpenAI Sora", "use Sora 2", or when generating video prompts and the movie settings specify Sora as the target platform. Provides best practices for OpenAI Sora 2 video generation prompts.
version: 0.1.0
---

# Sora 2 Prompting Guide

This skill provides comprehensive guidance for crafting effective prompts for OpenAI Sora 2 video generation. Sora excels at visually stunning, precisely controlled video with strong adherence to visual style.

## When to Use Sora vs Veo

Choose Sora when:
- Visual style consistency is paramount
- Working with 4, 8, or 12 second clips (longer than Veo's 8s max)
- Using reference images as first-frame anchors
- Audio is not required in the generated video

For dialogue, sound effects, or synchronized audio, consider the `veo-prompting` skill instead.

## Core Prompt Structure

Use a **storyboard approach** with clear sections:

```
[Scene Description]
Cinematography: [camera, mood, framing]
Actions: [specific beats with timing]
```

### Key Principles

1. **Specific visual language** - Replace vague terms with concrete details
2. **Style sets everything** - Establish aesthetic early
3. **Single clear action** - One camera move, one subject action per clip
4. **Precise timing** - Count beats, steps, seconds

## Specificity Over Vagueness

Sora responds dramatically better to specific, visual descriptions:

| Vague (Avoid) | Specific (Use) |
|---------------|----------------|
| Beautiful street at night | Wet asphalt, zebra crosswalk, neon signs reflecting in puddles |
| Person moves quickly | Cyclist pedals three times, brakes, and stops at crosswalk |
| Nice room | Velvet armchair, mahogany side table, brass reading lamp |
| Cinematic look | Anamorphic 2.0x lens, shallow DOF, volumetric light |

## Style Declaration

Establish the aesthetic early in the prompt. This frames all subsequent details:

```
1970s film grain, warm amber color grade, slight vignette

16mm black-and-white, high contrast, documentary texture

Modern digital, clean, saturated colors, pristine detail
```

## Action Beats and Timing

Structure actions with precise counts and pauses:

```
Actor takes four steps to window, pauses two beats,
reaches for curtain, pulls it aside in final second.
```

```
Hand enters frame from left, picks up coffee cup,
raises it to lips, holds, sets it back down.
```

### Separate Camera and Subject Motion

Describe them independently for clarity:

```
Camera: Slow dolly-in over eight seconds
Subject: Woman reads letter, expression shifts from
neutral to surprise at the three-second mark.
```

## Cinematography Terms

### Framing
- Wide establishing shot, eye level
- Medium shot, three-quarter angle
- Close-up, centered
- Over-the-shoulder

### Camera Motion
- Static/locked off
- Slow dolly-in
- Gentle pan left
- Handheld ENG camera
- Steadicam float

### Depth of Field
- Shallow (sharp on subject, blurred background)
- Deep focus (all elements sharp)
- Rack focus (shift between subjects)

## Lighting and Color Anchors

Describe both **light quality** and **color palette**:

```
Light: Soft window light with warm lamp fill, cool rim from hallway
Palette: Amber, cream, walnut brown
```

```
Light: Harsh overhead fluorescent, no fill, unflattering
Palette: Sickly green, institutional beige, cold white
```

## Reference Image Input

Sora accepts a static image as `input_reference` to lock composition and style:

1. Generate or source a reference image (JPEG, PNG, or WebP)
2. Match the image resolution to target output
3. The model treats it as the first frame anchor
4. Subsequent motion builds from this starting point

This is essential for character and set consistency across clips.

## Iteration with Remix

Make one controlled change at a time:

```
Same shot, switch to 85mm lens
Same lighting, new palette: teal, sand, rust
Same action, add slight camera shake
```

If a shot misfires:
1. Freeze the camera (static shot)
2. Simplify the action
3. Clear the background
4. Layer complexity back step by step

## Technical Specifications

| Parameter | Options |
|-----------|---------|
| Model | sora-2, sora-2-pro |
| Resolution | 1280x720, 720x1280 (both); 1024x1792, 1792x1024 (pro only) |
| Duration | 4, 8, or 12 seconds |
| Audio | Not generated (add in post) |

Note: Resolution, duration, and model are set via API, not in the text prompt.

## Silent Scene Audio Cues

Even for silent video, include one small sound cue for rhythm guidance:

```
Audio cue: Distant traffic hiss
Audio cue: Crisp snap of closing book
Audio cue: Soft breath exhale
```

This helps time the visual rhythm even though no audio is generated.

## What to Avoid

1. **Vague phrasing** - "Cinematic look" without specifics
2. **Conflicting traits** - Multiple focal points competing
3. **Long speeches** - Won't sync within clip duration
4. **Oversized prompts** - Constrains creative variation

## Prompt Length Balance

- **Detailed prompts** = Consistent, controlled results
- **Lighter prompts** = Diverse, surprising variations

Match the approach to the goal. For consistent character/set clips, be detailed. For exploration, keep it lighter.

## Reference Files

For extended vocabulary and advanced techniques:
- **`references/visual-vocabulary.md`** - Detailed visual description terms
- **`references/iteration-patterns.md`** - Systematic prompt refinement

## Example Prompts

Working examples for common scenarios:
- **`examples/portrait-shot.md`** - Character close-ups
- **`examples/environment-shot.md`** - Location and atmosphere
- **`examples/motion-sequence.md`** - Subject movement

## Best Practices Summary

1. Be visually specific - concrete details over vague terms
2. Establish style early - it frames everything else
3. One action per shot - single camera move, single subject action
4. Time in beats - steps, seconds, pauses
5. Separate camera and subject motion in description
6. Describe light quality AND color palette
7. Use reference images for consistency
8. Iterate with single controlled changes
9. Include rhythm cues even for silent output
