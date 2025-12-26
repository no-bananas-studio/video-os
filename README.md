# Video OS

AI movie production toolkit for creating consistent video clips using Google Veo and OpenAI Sora.

## Overview

Video OS helps you produce AI-generated movies by:
- Defining a consistent visual style across all clips
- Building reusable characters and sets with reference images
- Generating optimized prompts for Veo 3 and Sora 2
- Managing scenes within 10-20 second clip constraints
- Iterating on prompts based on generation feedback

## Workflow

1. **New Movie** (`/video-os:new-movie`) - Define style, mood, platform, and settings
2. **Story** (`/video-os:story`) - Develop narrative from your concept
3. **Characters** (`/video-os:character`) - Build characters with reference image prompts
4. **Sets** (`/video-os:set`) - Create locations with reference image prompts
5. **Scenes** (`/video-os:scene`) - Generate clip prompts using your characters and sets
6. **Review** (`/video-os:review`) - Iterate based on generation results

## Project Structure

Each movie project stores its data locally:

```
your-movie/
├── .video-os/
│   ├── movie.md          # Style, settings, story
│   ├── characters/       # Character definitions
│   ├── sets/             # Set/location definitions
│   └── scenes/           # Scene prompts and feedback
```

## Supported Platforms

- **Google Veo 3** - 4/6/8 second clips, audio support, 720p/1080p
- **OpenAI Sora 2** - 4/8/12 second clips, image anchoring, various resolutions

## Commands

| Command | Description |
|---------|-------------|
| `/video-os:new-movie` | Initialize a new movie project |
| `/video-os:story` | Develop the story from a concept |
| `/video-os:character` | Create or edit a character |
| `/video-os:set` | Create or edit a set/location |
| `/video-os:scene` | Generate a scene prompt |
| `/video-os:review` | Review and iterate on prompts |

## Installation

```bash
claude --plugin-dir /path/to/video-os
```

Or add to your Claude Code plugins directory.
