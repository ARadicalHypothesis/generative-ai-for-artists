---
title: Images in ComfyUI
module: "03"
description: Text-to-image, image-to-image, ControlNet and LoRAs with open models, run locally in ComfyUI.
prev: /modules/02-data-and-consent.html
prev_title: Data and consent
next: /modules/04-training-a-lora.html
next_title: Training a LoRA
---

# Images in ComfyUI

<p class="lede">Four workflows cover most image work: generate from text, transform an existing image, constrain the composition, and apply a style you trained. All four run locally with open models.</p>

## Choosing a model

Licences below are taken from each model's card on Hugging Face (checked October 2026). Licences change, so check again before you depend on one. "Weight" is a rough guide: light runs on 6–8 GB of VRAM, heavy wants 16–24 GB unless you use a quantized version.

| Model | Strengths | Weight | Licence |
|---|---|---|---|
| **Stable Diffusion 1.5** and community fine-tunes (e.g. Juggernaut Reborn) | Fast, huge ecosystem of LoRAs and ControlNets, very hackable | light | <span class="tag weights">CreativeML OpenRAIL-M</span> (use restrictions) |
| **SDXL** | Painterly and stylised work, abstraction; thousands of LoRAs | light to medium | <span class="tag weights">OpenRAIL++</span> |
| **Z-Image Turbo** (Tongyi-MAI, Alibaba) | Photorealism and lettering in very few steps | medium; FP8 and GGUF versions for smaller cards | <span class="tag open">Apache 2.0</span> |
| **FLUX.1 [schnell]** (Black Forest Labs) | Strong prompt-following in very few steps | heavy; FP8 versions help | <span class="tag open">Apache 2.0</span> |
| **FLUX.2 [klein] 4B** | A smaller member of the Flux family | medium | <span class="tag open">Apache 2.0</span> |
| **Qwen-Image** (Alibaba) | Complex layouts and lettering | heavy | <span class="tag open">Apache 2.0</span> |
| **FLUX.1 [dev]** | High quality, widely used | heavy | <span class="tag weights">non-commercial</span> |
| **CommonCanvas** | Trained on Creative Commons images (see [module 02](02-data-and-consent.md)) | light | <span class="tag open">CC BY-SA 4.0</span> |

**SDXL or Flux-family?** SDXL works more like a painter. Its convolutional network learns textures and shapes in patches, so it bends easily into abstract and stylised looks, but it struggles with spelling and with spatial logic ("a cat *on* a box"). Flux and the other flow-matching transformers work more like a language model. They track how the parts of an image relate, so they handle text, hands and complex prompts, but they're heavier and have a recognisable smooth "AI realism" that's hard to shake. Use SDXL for experiments and stylised work, and the transformer models when you need precision.

## The four workflows

Open each one from ComfyUI's **Templates** menu, or load Pixaroma's free "Getting Started" workflows (see [Start here](00-start-here.md)). Each model node notes where to download its model and which folder to put it in.

### 1. Text to image

`Load Checkpoint → CLIP Text Encode (positive / negative) → KSampler → VAE Decode → Save Image`

Learn what each KSampler setting does by changing one at a time: **seed** (the starting noise), **steps**, **CFG** (how strictly the prompt is followed), **sampler** and **scheduler**. Keep the seed fixed while you change everything else. That's how you learn the model, rather than gambling on it.

### 2. Image to image

Replace the empty latent with **Load Image → VAE Encode**. The **denoise** value decides how much of your source survives: around 0.3 keeps it recognisable, around 0.7 keeps only its composition. This is the workflow that lets your own drawings, photos and renders lead.

### 3. ControlNet

Extract a structure from a reference image (edges with Canny, depth, pose, lineart) and make the generation follow it. You get compositional control without prompt gymnastics. ControlNet models exist for SD 1.5, SDXL and Z-Image (the *Z-Image-Turbo Fun ControlNet Union* model).

### 4. LoRA

Add a **LoRA Loader** after the checkpoint to apply a small trained add-on: a style, a character, an object. Strength around 0.6–1.0. Use **your own** LoRA (see [module 04](04-training-a-lora.md)) and the work stops looking like everyone else's.

## Upscaling

Find the image at low resolution, then upscale only what you keep. Open-source upscalers such as [Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN) (BSD-3) run inside ComfyUI. A light second img2img pass at higher resolution adds detail. Commercial "creative upscalers" like Magnific and Topaz do the same job behind a subscription.

## Beyond ComfyUI

- [InvokeAI](https://github.com/invoke-ai/InvokeAI) (Apache 2.0): an open-source, canvas-based interface, good for inpainting and painting-like work.
- [Diffusers](https://github.com/huggingface/diffusers) (Apache 2.0): Hugging Face's Python library, for people who want to script.
- [Dream Textures](https://github.com/carson-katri/dream-textures) (GPL-3.0): Stable Diffusion inside Blender, for textures and render passes.
- [Stable Diffusion Tools for Unreal](https://github.com/Mystfit/Unreal-StableDiffusionTools) (MIT): generation inside Unreal Engine.

## Exercise

**Image to image with your own LoRA.** Build the img2img + LoRA workflow. Using a LoRA you trained, or an openly licensed one, make at least five stylised images: a landscape, a character, an object. For each, record the model, LoRA, seed, steps, CFG and denoise, and write one sentence on what changed and why.
