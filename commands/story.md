---
name: story
description: Develop the movie's narrative structure from a basic concept, optimizing for AI video generation strengths
argument-hint: "[story concept or idea]"
allowed-tools:
  - Read
  - Write
  - Edit
  - AskUserQuestion
---

# Develop Story

Transform a basic concept into a structured narrative optimized for AI video generation. This command helps build a story that plays to the strengths of Veo and Sora while working within their constraints.

## Prerequisites

Ensure the movie project exists by reading `.video-os/movie.md`. If it doesn't exist, suggest running `/video-os:new-movie` first.

## AI Video Generation Strengths

Guide the story toward elements that AI video excels at:

**Visual Clarity:**
- Stark, uncluttered environments
- Clear visual contrast between elements
- Distinct silhouettes and shapes
- Simple, readable compositions

**Atmospheric Settings:**
- Empty or sparsely populated spaces
- Strong lighting conditions (golden hour, neon, dramatic shadows)
- Weather and atmosphere (fog, rain, dust, light rays)
- Iconic, recognizable locations

**Manageable Action:**
- Single focused actions per scene
- Clear cause and effect
- Minimal complex interactions
- Emotional moments over elaborate choreography

**Consistency Opportunities:**
- Recurring characters (with reference images)
- Returning locations (with set references)
- Consistent color palette
- Uniform visual style

## Workflow

### Step 1: Capture the Concept

If no concept is provided, ask:
- What is the basic premise or idea?
- What genre or tone are you aiming for?
- What is the emotional journey?
- Any specific images or moments you envision?

### Step 2: Develop Structure

Ask clarifying questions to fill in gaps:

**Beginning:**
- How does the story open?
- What world/situation are we entering?
- What is the initial state of the character(s)?

**Middle:**
- What changes or challenges occur?
- What is the turning point?
- How do characters transform?

**End:**
- How does the story resolve?
- What is the final image or moment?
- What emotion should the audience feel?

### Step 3: Break into Scenes

Create a scene-by-scene breakdown:

```markdown
## Scene Breakdown

### Scene 1: [Title]
- **Duration**: ~[X] seconds ([N] clips)
- **Location**: [Set name or description]
- **Characters**: [Who appears]
- **Action**: [What happens]
- **Purpose**: [Why this scene matters]

### Scene 2: [Title]
...
```

**Duration Guidance:**
- Each clip is 4-12 seconds depending on platform
- A 2-minute movie = ~12-30 clips
- A 5-minute movie = ~30-75 clips
- A 15-minute movie = ~90-225 clips

### Step 4: Identify Requirements

List what needs to be created:

**Characters Needed:**
- Character A: [brief description]
- Character B: [brief description]

**Sets Needed:**
- Location 1: [brief description]
- Location 2: [brief description]

### Step 5: Update movie.md

Add the story section to `.video-os/movie.md`:

```markdown
## Story

### Premise
[One paragraph summary]

### Structure
[Beginning/Middle/End outline]

### Scene Breakdown
[List of scenes with details]

### Characters Required
[List with brief descriptions]

### Sets Required
[List with brief descriptions]
```

### Step 6: Next Steps

Recommend the workflow:
1. Create characters with `/video-os:character`
2. Create sets with `/video-os:set`
3. Generate scenes with `/video-os:scene`

## Tips

- Keep scenes visually distinct from each other
- Favor environmental storytelling over dialogue-heavy scenes
- Consider how scenes will transition (visual continuity)
- Plan for consistent character appearance across all scenes
- Suggest simplifications if the story becomes too complex
- Each scene should have ONE clear visual focus
