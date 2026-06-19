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
2. For industry-hotspot topics, follow: hotspot discovery -> topic scoring -> content production -> image/video production -> Google Drive sync.
3. Search the web before writing. Prefer recent B2B buyer behavior, trade trends, customs/export data, platform rules, buyer pain points, and practical foreign-trade workflows.
4. Choose a non-duplicative topic by checking existing `generated_content/` folders and prior `note.md` / `preview.txt` files.
5. For daily batches, prefer a balanced mix: one industry trend, one practical foreign-trade tutorial, and one mistake/case/checklist post.
6. Create one English-safe output folder:
   - `generated_content/YYYY-MM-DD-NN-english-topic-slug/`
   - Use lowercase English, digits, and hyphens only. Do not use Chinese, spaces, or special characters in folder names.
7. Produce all required files:
   - `cover.png`
   - `image-01.png` through `image-07.png` to `image-09.png`
   - `note.md`
   - `preview.txt`
   - `prompts.md`
   - `sources.md`
   - `video-script.md`
   - `carousel-video.mp4`
8. Sync the completed folder to Google Drive after local validation.

## Skill and Plugin Routing

- Use this skill as the main workflow controller.
- Use web search for ordinary hotspot collection.
- Use `deep-research` when the user asks for a deeper trend scan or when the topic depends on multiple current sources.
- Use `imagegen` for cover and content images after `prompts.md` is written.
- Use `FFmpeg Video Editor` or local FFmpeg for `carousel-video.mp4`.
- Use `Google Drive` to sync completed packages.
- Use `GitHub` for maintaining this skill and publishing rule changes.

## Hotspot Topic Selection

Collect 5-10 recent foreign-trade hotspots before selecting topics.

Prefer these sources:

- Official or authoritative sources: customs data, commerce ministries, WTO, UNCTAD, FedEx/DHL/UPS reports, and platform announcements.
- Industry trends: B2B buyer reports, AI sourcing, cross-border ecommerce shifts, trade shows, and popular export categories.
- Practical pain points: seller communities, buyer behavior, inquiry replies, quotation problems, logistics, tariffs, exchange rates, and customer-development changes.

Score topics by:

- Relevance to daily foreign-trade work.
- Ability to produce actionable advice.
- Suitability for Xiaohongshu/Douyin titles.
- Non-duplication against existing generated content.

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
- Start `prompts.md` with one unified visual style statement for the whole post, then write each image prompt.
- Keep text in images short, large, and readable.
- Prefer vertical social formats for Xiaohongshu and Douyin.
- Use the project style guide unless the user requests a different style.
- Avoid fake logos, watermarks, unreadable tiny text, and highly repetitive layouts.
- Keep all images in the same post visually unified: same primary palette, typography feel, card style, icon style, and layout density. Vary composition, but do not mix conflicting styles such as realistic, comic, cyberpunk, and minimalist in one post.

Use image generation skills/tools when available. For project-bound images, copy final assets into the content folder and keep original generated files intact.

## Carousel Video

Create `carousel-video.mp4` from the cover and content images.

- Use a vertical 1080x1920 canvas by default.
- Play cover first, then content images in filename order.
- Use gentle transitions such as fade or slide.
- Keep total duration under 15 seconds.
- Default timing: cover 1.5-2 seconds, each content image 1.2-1.5 seconds, transitions 0.2-0.35 seconds.
- When there are many images, shorten per-image duration instead of dropping required content images.
- Keep the video silent unless the user asks for music or voiceover.
- If the user asks for music or voiceover, still keep total duration under 15 seconds.
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
- `prompts.md` declares the unified visual style and includes prompt text for every image.
- Images in the same post use a unified visual style.
- `carousel-video.mp4` exists, uses the generated images with transitions, is vertical, and is under 15 seconds.
- Completed files are synced to Google Drive and verified.
