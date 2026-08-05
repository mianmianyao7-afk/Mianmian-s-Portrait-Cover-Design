---
name: portrait-video-cover
description: Create bold Chinese video and social-media cover images from a user's portrait and video topic, with selectable 16:9, 4:3, 3:4, 9:16, or 1:1 output sizes, skin brightening and smoothing, flexible creator poses, oversized outlined headlines, and clean tech-style supporting graphics. Use when users ask to make 视频封面、公众号封面、YouTube thumbnail、小红书封面、抖音/视频号竖屏封面、人物口播封面, or request a cover matching the bundled reference style.
---

# Portrait Video Cover

Create a polished bitmap cover through a fixed, user-guided workflow. Use the `imagegen` skill and its image-generation/editing tool for all portrait editing and final image generation.

## Required interaction order

### 1. Ask for the aspect ratio first

Make the first reply a single-choice question. Do not ask for the portrait, title, style, or other information yet.

Use these exact choices:

- 16:9（YouTube）
- 4:3（经典）
- 3:4（小红书）
- 9:16（抖音、视频号竖屏）
- 1:1（方形）

Map the choice to:

| Choice | Canvas |
|---|---:|
| 16:9 | 1920 × 1080 |
| 4:3 | 1600 × 1200 |
| 3:4 | 1080 × 1440 |
| 9:16 | 1080 × 1920 |
| 1:1 | 1080 × 1080 |

### 2. Request the user's portrait

After the user chooses a ratio, ask them to upload one clear, original-resolution photo of themselves. Recommend:

- face and hair fully visible;
- front-facing or three-quarter view;
- even lighting and no strong beauty filter;
- upper body visible when possible;
- no other people blocking the subject.

Do not generate the final cover before receiving the portrait. If the photo is unusable, explain the specific issue and ask for a replacement.

### 3. Ask for the video topic or short description

After receiving and inspecting the portrait, ask the user to enter the video topic or a short description. Accept a short sentence, outline, transcript, or spoken-script excerpt. Use a prompt such as:

> 请介绍一下视频主题，或者粘贴一段视频简短描述/口播内容。

Derive a short, punchy main title and optional subtitle from the description. Present the proposed copy and obtain confirmation before generating. Split the main title into 2–3 meaningful visual rows.

If the user already supplies explicit cover copy, retain it unless it is too long. Also accept optional logos, product screenshots, phone/app interfaces, and brand colors. Infer sensible defaults when optional information is absent.

### 4. Retouch the portrait

Edit the uploaded portrait before composing the cover. Preserve identity, age range, facial structure, recognizable features, and natural skin texture. The cover may adapt the pose, gesture, expression, framing, and props to communicate the video topic.

Apply all of these natural retouching requirements:

- 美白皮肤：slightly brighten and even the complexion; retain pores and natural color.
- 自然磨皮：soften rough texture and minor blemishes evenly while retaining pores, facial contours, and realistic skin detail; avoid waxy or plastic skin.
- 去油光：reduce forehead, nose, and cheek shine without creating flat plastic skin.
- 高颅顶：subtly increase the visual height above the hairline with anatomically plausible hair volume.
- 头发蓬松：add natural root lift and separation; preserve hairline, strand direction, and original hair color.

Also remove temporary-looking minor blemishes and distracting flyaway hairs. Do not enlarge eyes, sharpen the chin, narrow the face, alter ethnicity, replace the face, or erase all skin texture unless the user explicitly requests it.

Allow cover-friendly pose generation. The person may point at a supporting object, hold a microphone, hold a phone, gesture toward the headline, or use another topic-relevant creator pose. Match hands, props, lighting, clothing, and body anatomy believably. Prefer a handheld microphone for spoken commentary, tutorials, announcements, and creator-led explanations when it strengthens the composition.

### 5. Compose the cover

Read [references/style-guide.md](references/style-guide.md) before composing. Use the images in `assets/references/` as visual references, not as content to copy into the output.

Default composition:

- bright white or near-white background with subtle lavender/mint brush textures;
- very large, heavy black Chinese headline with thick white keyline;
- soft lavender and mint offset shadows behind the title for a sticker-like layered effect;
- retouched person cut out cleanly, usually in the lower-left or lower-center;
- a topic-relevant creator pose; freely add a handheld microphone, pointing gesture, phone, or other useful prop when it improves storytelling;
- one main supporting object or interface on the opposite side;
- a clear gesture, gaze, arrow, or dotted path connecting the person to the supporting object;
- sparse tech-themed cards, sparkles, arrows, or mascot-like accents;
- generous safe margins and strong thumbnail readability.

Adapt the layout to the chosen ratio instead of mechanically cropping:

- 16:9 and 4:3: favor left/right balance and wide title blocks.
- 3:4 and 9:16: stack title, portrait, and supporting object vertically; protect the face from platform UI overlays.
- 1:1: use a compact triangular composition and reduce secondary decoration.

Render all supplied Chinese text exactly. If image generation produces illegible or incorrect text, regenerate or use a deterministic text-overlay method available in the environment. Never deliver garbled headline text.

### 6. Verify and deliver

Inspect the final image before delivery. Confirm:

- exact requested aspect ratio and dimensions;
- identity is preserved and retouching is natural;
- skin is visibly brightened and smoothly retouched without plastic texture;
- any generated pose, gesture, microphone, or prop is intentional, anatomically plausible, and not accidentally cropped;
- headline is correct, readable, and dominant at thumbnail size;
- no warped hands, duplicated fingers, distorted phone edges, fake logos, or garbled UI text;
- all user-supplied assets are used accurately;
- no reference-image person, logo, or private content appears unless the user explicitly supplied it for this output.

Show the generated cover and state its pixel dimensions. Offer one concise revision round focused on title, layout, colors, portrait retouching strength, or supporting graphics.

## Privacy

Treat portraits as sensitive user content. Use them only for the requested cover. Do not package, publish, or reuse a user's portrait as a reusable skill asset without explicit permission.
