---
title: Video and animation
module: "05"
description: Open video models, motion control, real-time diffusion and motion capture, with the closed platforms studied critically.
prev: /modules/04-training-a-lora.html
prev_title: Training a LoRA
next: /modules/06-3d-and-space.html
next_title: 3D and space
---

# Video and animation

<p class="lede">Video is where the closed platforms are most aggressive and most expensive. It's also where open models have caught up fastest, and where the real computing cost of generative AI becomes impossible to ignore.</p>

## Open video models

| Model | What it does | Licence |
|---|---|---|
| [Wan 2.2](https://github.com/Wan-Video/Wan2.2) (Alibaba) | Text-to-video and image-to-video; a 5B model for smaller GPUs and 14B models for quality. The current open baseline. | <span class="tag open">Apache 2.0</span> |
| [LTX-Video](https://github.com/Lightricks/LTX-Video) / LTX-2 (Lightricks) | Fast video generation, built for iteration | <span class="tag weights">code Apache 2.0; weights under Lightricks' own licence</span> |
| [HunyuanVideo](https://github.com/Tencent-Hunyuan/HunyuanVideo) (Tencent) | High-quality text-to-video | <span class="tag weights">Tencent community licence; excludes the EU, UK and South Korea</span> |
| Stable Video Diffusion (Stability AI) | Image-to-video; older | <span class="tag weights">Stability community licence</span> |
| [AnimateDiff](https://github.com/guoyww/AnimateDiff) | Adds motion to SD 1.5 and SDXL; the basis of many stylised animation workflows | <span class="tag open">Apache 2.0</span> |

In ComfyUI, Wan runs through the native nodes or Kijai's [WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper) (Apache 2.0). Start with the 5B model at low resolution and a short clip, and only scale up once the motion works.

## Directing motion instead of prompting it

- **Time-to-Move + Wan 2.2.** [Time-to-Move](https://time-to-move.github.io/) (Apache 2.0) lets you sketch motion by dragging cut-out regions of a frame, then generates video that follows your path. You direct the movement instead of describing it. Watch: [Stop Prompting. Start Directing](https://www.youtube.com/watch?v=HvRwJGzOAj4) (Comfy Compositing). ComfyUI workflow: [AI-Time2Move-Comfyui](https://github.com/rik-python/AI-Time2Move-Comfyui).
- **Rendering 3D with diffusion.** Animate simple clay or grey-shaded scenes in Blender, then use depth and ControlNet passes to "render" them with a diffusion model. 3D stays in charge of motion and composition, and AI becomes a finishing layer. Watch: [Render 3D animations with Blender + Stable Diffusion](https://www.youtube.com/watch?v=8afb3luBvD8) and [AI renderings of your 3D animations](https://www.youtube.com/watch?v=mu3JEfx3PHM) (Mickmumpitz).
- **MagicAnimate** ([code](https://github.com/magic-research/magic-animate), BSD-3): animates a single image of a person from a motion video.

## Real time: StreamDiffusion in TouchDesigner

[StreamDiffusion](https://github.com/cumulo-autumn/StreamDiffusion) (Apache 2.0) runs diffusion fast enough for live input: cameras, sensors, performers. **StreamDiffusionTD**, a TouchDesigner component by DotSimulate, brings it into TouchDesigner for installations, VJ sets and performance. It can run on your own NVIDIA GPU or on a cloud backend. Running locally is the choice that keeps the work self-contained. Watch: [StreamDiffusionTD installation](https://www.youtube.com/watch?v=F2JSWAKex4k) and [0.3.0 overview](https://www.youtube.com/watch?v=v8ktcj-gFLA) (dotsimulate).

New to TouchDesigner? See the companion open course, [TouchDesigner for Artists](https://github.com/ARadicalHypothesis/touchdesigner-for-artists).

## Motion and motion capture

| Tool | What it does | Licence |
|---|---|---|
| [FreeMoCap](https://github.com/freemocap/freemocap) | Markerless motion capture from ordinary webcams | <span class="tag open">AGPL-3.0</span> |
| [MDM: Human Motion Diffusion Model](https://github.com/GuyTevet/motion-diffusion-model) | Generates body motion from a text description | <span class="tag open">MIT</span> |
| [MotionDiffuse](https://github.com/MotrixLab/MotionDiffuse) | Text-driven motion generation | see repository |
| Blender + retargeting | Move captured or generated motion onto your own rigged characters | <span class="tag open">GPL</span> (Blender) |
| Cascadeur, Move.ai, Plask, Mootion, Motorica | Commercial AI-assisted animation and capture | <span class="tag closed">service / proprietary</span> |

## The closed platforms, studied critically

Google's **Veo 3.1 / Flow**, OpenAI's **Sora 2**, **Kling 3.0** and **Runway** set the visual benchmark many people now measure against. Learn what they do. Then notice what you give up to use them:

- **No custom models.** Flow, for example, doesn't accept your own LoRAs or models. You get reference images at most, so your aesthetic is bounded by theirs.
- **Undisclosed training data.** None of them publishes what it learned from. Video models have drawn copyright complaints from film studios and rights holders. Watch: [ByteDance pledges fixes to Seedance 2.0 after Hollywood copyright claims](https://www.youtube.com/watch?v=hYO-iEGnPX0) (Al Jazeera).
- **Rented, metered, changeable.** Credits, tiers and terms change without notice, and so can the model itself. Your workflow can disappear.
- **The most energy-intensive kind of generation.** Video multiplies the cost of an image by every frame (see [module 09](09-sustainable-practice.md)).

Watch, critically: [Creating in Flow](https://www.youtube.com/watch?v=9nVEfjmDlVk) (Google) · [OpenAI tool creates realistic AI videos](https://www.youtube.com/watch?v=anmuklFtu8U) (WSJ) · [Camera movement prompts](https://www.youtube.com/watch?v=zQI_pWw9qWo): useful on any platform.

## Exercise

**One brief, two systems.** Write a 30-second brief. Make it once with an open model running locally (Wan 2.2, LTX or AnimateDiff, with your own LoRA or reference material) and once with a closed platform. Compare control, time, cost, energy (see [module 09](09-sustainable-practice.md)) and what you know about each model's training data. Present both, and argue for one.

**Or, experimental:** build one of the directed-motion workflows above (Time-to-Move, a diffusion-rendered 3D scene, or a StreamDiffusion patch in TouchDesigner) and document the process in a few slides.
