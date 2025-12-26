---
name: review
description: Review generated video results and iterate on prompts based on feedback
argument-hint: "[scene name/number to review]"
allowed-tools:
  - Read
  - Write
  - Edit
  - AskUserQuestion
---

# Review and Iterate on Scene Prompts

Record feedback from generated video clips and create improved prompt iterations. This command helps refine prompts based on actual generation results.

## Prerequisites

Read the scene file from `.video-os/scenes/` to understand the original prompt and context.

## Workflow

### Step 1: Identify Scene

If a scene is specified, load it. Otherwise, list available scenes and ask which to review:

```
Available scenes:
1. Scene 01: Opening - diner exterior
2. Scene 02: Meeting - diner interior
...
Which scene would you like to review?
```

### Step 2: Gather Feedback

Ask the user about the generation results:

**Overall Assessment:**
- Did the generation work? (Success / Partial / Failed)
- What worked well?
- What didn't work?

**Specific Issues** (ask about each if relevant):

**Character Issues:**
- Did the character look correct?
- Was the face/appearance consistent with reference?
- Were clothing/accessories accurate?
- Was the body language/action correct?

**Set/Environment Issues:**
- Did the location look right?
- Were key features visible?
- Was the lighting/atmosphere correct?
- Any unwanted elements appear?

**Action/Timing Issues:**
- Did the action happen as described?
- Was the timing correct?
- Was the camera movement smooth?
- Any unexpected motion?

**Style Issues:**
- Did it match the movie's visual style?
- Was the color palette correct?
- Did the film grain/texture look right?
- Was the mood appropriate?

**Audio Issues (Veo only):**
- Was dialogue clear and correctly timed?
- Were sound effects appropriate?
- Was ambient audio fitting?

### Step 3: Diagnose Problems

Based on feedback, identify likely prompt issues:

| Problem | Likely Cause | Fix Approach |
|---------|--------------|--------------|
| Wrong character appearance | Description too vague | Add specific physical details |
| Inconsistent face | Missing reference image | Include character reference |
| Wrong action | Timing unclear | Add beat counts/seconds |
| Too much happening | Prompt too complex | Simplify to single action |
| Wrong lighting | Implicit assumption | Explicitly describe light |
| Wrong style | Style keywords too late | Move style to beginning |
| Chaotic result | Too many elements | Strip back, rebuild |

### Step 4: Create Revised Prompt

Generate an improved prompt addressing the issues:

**Strategy 1: Precision Refinement**
- Add specific details where vague
- Include explicit timing
- Strengthen style keywords

**Strategy 2: Simplification**
- Remove competing elements
- Focus on single action
- Clear the background

**Strategy 3: Reference Adjustment**
- Different reference image angle
- Add missing character reference
- Use different set variant

Present the revised prompt and explain what changed:

```
## Revised Prompt (Attempt 2)

Changes from original:
- Added explicit timing: "At second 2, she looks up"
- Simplified action: removed secondary movement
- Strengthened style: moved "film noir" to beginning
- Added character reference: "three-quarter portrait variant"

[New prompt here]
```

### Step 5: Update Scene File

Add the generation attempt and feedback to the scene file:

```markdown
## Generation Log

### Attempt 1
- **Date**: [date]
- **Platform**: [Veo/Sora]
- **Result**: [outcome]
- **What Worked**: [positive notes]
- **Issues**: [problems encountered]
- **Prompt Used**:
```
[original prompt]
```

### Attempt 2
- **Date**: [date]
- **Platform**: [Veo/Sora]
- **Result**: [pending]
- **Changes Made**: [what was adjusted]
- **Prompt Used**:
```
[revised prompt]
```
```

### Step 6: Track Successful Patterns

If a prompt worked well, note the successful patterns for future reference:

```markdown
## Successful Patterns

- [What worked and why]
- [Specific phrasing that helped]
- [Reference image combination that worked]
```

These patterns can inform prompts for similar scenes.

### Step 7: Next Steps

Based on outcome:

**If revision needed:**
- Try the new prompt
- Return with `/video-os:review` to continue iteration

**If successful:**
- Mark scene as complete
- Move to next scene
- Consider if patterns apply to other scenes

**If repeatedly failing:**
- Suggest scene restructuring
- Consider splitting into multiple clips
- Recommend simplifying the concept

## Common Fixes

### "Character looks wrong"
Add more physical specifics, ensure reference image is included, match lighting between reference and scene

### "Action is unclear or wrong"
Time action in beats/seconds, reduce to single clear action, separate camera and subject motion

### "Style isn't matching"
Move style keywords to start of prompt, add specific technical terms (lens, film stock), reference movie's style file

### "Too chaotic"
Strip to simplest version, static camera, single subject, plain background—then add back one element at a time

### "Lighting is off"
Explicitly describe light direction, color temperature, sources; don't rely on implicit assumptions
