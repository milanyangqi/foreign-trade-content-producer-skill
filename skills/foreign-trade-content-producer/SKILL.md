---
name: foreign-trade-content-producer
description: Produce Chinese foreign-trade creator content packages for Xiaohongshu and Douyin. Use when Codex needs to research international trade topics, create non-duplicative daily posts, generate cover/content image prompts and images, build carousel videos, create mobile preview text, organize output folders with English-safe paths, and sync completed packages to Google Drive.
---

# Foreign Trade Content Producer

Use this skill to generate complete content packages for a Chinese foreign-trade blogger.

## Core Workflow

1. Read the local project rules first:
   - `agents.md` for required deliverables, folder policy, naming, validation, and Google Drive sync.
   - `content_style_guide.md` for reusable visual styles.
2. Search the web before writing. Prefer recent B2B buyer behavior, trade trends, customs/export data, platform rules, buyer pain points, and practical foreign-trade workflows.
3. Choose a non-duplicative topic by checking existing `generated_content/` folders and prior `note.md` / `preview.txt` files.
4. Create one English-safe output folder:
   - `generated_content/YYYY-MM-DD-NN-english-topic-slug/`
   - Use lowercase English, digits, and hyphens only. Do not use Chinese, spaces, or special characters in folder names.
5. Produce all required files:
   - `cover.png`
   - `image-01.png` through `image-07.png` to `image-09.png`
   - `note.md`
   - `preview.txt`
   - `prompts.md`
   - `sources.md`
   - `video-script.md`
   - `carousel-video.mp4`
6. Sync the completed folder to Google Drive after local validation.

## Text Requirements

`note.md` must include:

- Chinese title suitable for Xiaohongshu and Douyin.
- Chinese body under 1000 characters.
- Exactly 5 hashtags.
- Source notes or references after the main content when useful.

`preview.txt` must be regenerated from `note.md` for mobile preview:

- Include only title, body, and exactly 5 hashtags.
- Use plain text only, without Markdown markers, source links, image prompts, or execution notes.

## Image Requirements

Generate the image prompts before generating images.

- Create 1 cover image and 7-9 content images.
- Store all prompts in `prompts.md`.
- Keep text in images short, large, and readable.
- Prefer vertical social formats for Xiaohongshu and Douyin.
- Use the project style guide unless the user requests a different style.
- Avoid fake logos, watermarks, unreadable tiny text, and highly repetitive layouts.

Use image generation skills/tools when available. For project-bound images, copy final assets into the content folder and keep original generated files intact.

## Carousel Video

Create `carousel-video.mp4` from the cover and content images.

- Use a vertical 1080x1920 canvas by default.
- Play cover first, then content images in filename order.
- Use gentle transitions such as fade or slide.
- Keep the video silent unless the user asks for music or voiceover.
- If video tooling has trouble with Chinese paths, copy images to an ASCII-only temporary directory, render there, then copy the final MP4 back.

## Google Drive Sync

After local validation, sync the completed folder to Google Drive.

- Create or reuse `International_trade/generated_content/YYYY-MM-DD-NN-english-topic-slug/`.
- Upload every completed file, including `preview.txt` and `carousel-video.mp4`.
- List the Drive folder after upload and confirm that all files are present.
- If an existing same-name Drive folder exists, verify it is the same content package before updating or uploading new versions.

## Validation Checklist

Before finishing:

- Folder name is English-safe and under `generated_content/`.
- No generated package folder is placed in the project root.
- The topic is not a repeat of existing generated content.
- `note.md` contains title, body under 1000 Chinese characters, and 5 hashtags.
- `preview.txt` contains only title, body, and 5 hashtags.
- There is 1 cover image and 7-9 content images.
- `prompts.md` includes prompt text for every image.
- `carousel-video.mp4` exists and uses the generated images with transitions.
- Completed files are synced to Google Drive and verified.
