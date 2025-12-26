# Sora Iteration Patterns

Systematic approaches to refining Sora prompts based on output feedback.

## The Single-Variable Method

Change only one element at a time to understand cause and effect:

### Baseline Prompt
```
Medium shot, woman in blue dress sits at cafe table,
morning light from window, looks up from book.
Style: 35mm film, warm tones.
```

### Iteration Examples

**Changing camera only:**
```
Close-up, woman in blue dress sits at cafe table,
morning light from window, looks up from book.
Style: 35mm film, warm tones.
```

**Changing lighting only:**
```
Medium shot, woman in blue dress sits at cafe table,
harsh overhead fluorescent, looks up from book.
Style: 35mm film, warm tones.
```

**Changing action only:**
```
Medium shot, woman in blue dress sits at cafe table,
morning light from window, closes book and sighs.
Style: 35mm film, warm tones.
```

## The Simplification Pattern

When outputs are chaotic, strip back and rebuild:

### Step 1: Maximum Simplicity
```
Static shot, empty cafe interior, morning.
```

### Step 2: Add Subject
```
Static shot, woman sits alone in empty cafe, morning light.
```

### Step 3: Add Detail
```
Static shot, woman in blue dress sits at marble-top cafe table,
morning light from large window behind her.
```

### Step 4: Add Action
```
Static shot, woman in blue dress sits at marble-top cafe table,
morning light from large window. She picks up coffee cup,
sips, sets it down.
```

### Step 5: Add Style
```
Static shot, woman in blue dress sits at marble-top cafe table,
morning light from large window. She picks up coffee cup,
sips, sets it down.
Style: French New Wave, slightly desaturated, natural.
```

## The Palette Swap Pattern

Keep everything identical except color/lighting:

### Original
```
Interior diner, red vinyl booths, chrome accents, noon sunlight.
Palette: Cherry red, cream white, chrome silver.
```

### Variation 1: Night
```
Interior diner, red vinyl booths, chrome accents, neon sign glow.
Palette: Deep crimson, warm amber, electric blue.
```

### Variation 2: Nostalgic
```
Interior diner, red vinyl booths, chrome accents, faded afternoon.
Palette: Dusty rose, aged cream, tarnished silver.
```

## The Lens Swap Pattern

Same scene through different virtual lenses:

### Wide Angle (24mm)
```
Wide shot, 24mm lens, slight barrel distortion, deep focus.
Man walks through grand cathedral, pillars stretching to ceiling.
```

### Normal (50mm)
```
Medium shot, 50mm lens, natural perspective, moderate depth of field.
Man walks through grand cathedral, pillars in soft background.
```

### Telephoto (135mm)
```
Medium close-up, 135mm lens, compressed background, shallow DOF.
Man walks through grand cathedral, pillars flattened behind.
```

## The Movement Modifier Pattern

Adjust quality of movement for different effects:

### Smooth/Graceful
```
She moves fluidly across the room, each step deliberate and unhurried,
hand trailing along the back of the sofa.
```

### Hesitant/Uncertain
```
She moves hesitantly across the room, pausing mid-step, hand reaching
toward the sofa then pulling back.
```

### Urgent/Rushed
```
She crosses the room quickly, nearly stumbling, hand catching the
sofa back for balance.
```

## The Specificity Ladder

Gradually increase detail until desired fidelity is reached:

### Level 1: General
```
Person enters room.
```

### Level 2: Character
```
Young woman enters library.
```

### Level 3: Action
```
Young woman pushes through heavy oak library doors,
scanning the room.
```

### Level 4: Detail
```
Young woman in oversized cardigan pushes through heavy oak
library doors, pausing as her eyes adjust to dim light,
then scanning rows of shelves.
```

### Level 5: Atmosphere
```
Young woman in oversized cream cardigan pushes through heavy
oak library doors, dust motes swirling in the shaft of light
from behind her. She pauses as her eyes adjust to the amber
glow of green-shaded reading lamps, then scans endless rows
of leather-bound spines.
```

## Debugging Common Issues

### Problem: Unintended Subject
**Symptom:** Wrong person/object becomes focus
**Fix:** Add "centered" or "subject is" to clarify focus

### Problem: Wrong Time of Day
**Symptom:** Lighting doesn't match intent
**Fix:** Be explicit: "3 PM afternoon sun" not just "afternoon"

### Problem: Style Not Applying
**Symptom:** Generic modern look despite style prompt
**Fix:** Move style to beginning, add specific technical terms

### Problem: Action Unclear
**Symptom:** Subject seems frozen or doing wrong thing
**Fix:** Time the action: "In the first two seconds, she..."

### Problem: Too Much Happening
**Symptom:** Chaotic, unfocused output
**Fix:** Remove elements until clean, then add back selectively

## Tracking Iterations

Document each attempt:

```
Version 1: [baseline prompt]
Result: Subject too dark, action unclear
Change: Added "well-lit" and timed action to "first 3 seconds"

Version 2: [modified prompt]
Result: Lighting good, action still unclear
Change: Simplified action to single gesture

Version 3: [modified prompt]
Result: Clean and clear
Final: Use this version
```
