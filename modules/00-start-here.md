---
title: Start here
module: "00"
description: The position this toolkit takes, and how to set up a local, open generative AI studio.
next: /modules/01-how-it-works.html
next_title: How these systems work
---

# Start here

<p class="lede">Generative AI reaches most artists as a subscription: a text box on someone else's server, trained on data nobody asked for, priced and changed at a company's discretion. This toolkit starts from the opposite end.</p>

## The position

Three principles run through every module:

1. **Open first.** Where an open-source tool or an openly licensed model can do the job, we learn that one. Closed services are studied too, as objects of critique and comparison, not as defaults.
2. **Local and accountable.** Running models on your own machine means you know what is running, your material doesn't leave your computer, and you can see the energy it uses. When you do use a cloud service, you should know what you are trading for it.
3. **Data with consent.** What a model learned from is part of what it is. We favour models and datasets built from public-domain, openly licensed or opt-in material, and we build our own datasets from work we have the right to use.

None of this is a purity test. Open tools have their own problems: some "open" models come with licences that restrict who may use them and where. The point is to make informed choices, and to keep the means of making art in the hands of the people who make it.

## "Open" is not one thing

The word gets stretched, so we use four labels throughout:

| Label | What it means | Example |
|---|---|---|
| <span class="tag open">open source</span> | Code (and weights, for a model) under a standard open licence such as MIT, Apache 2.0 or GPL. You can run, study, modify and share it. | ComfyUI (GPL-3.0), Wan 2.2 (Apache 2.0), TRELLIS.2 (MIT) |
| <span class="tag weights">open weights, restricted</span> | You can download and run the model, but its licence limits use: non-commercial only, revenue thresholds, or excluded countries. | FLUX.1 [dev], HunyuanVideo, Stable Audio Open |
| <span class="tag closed">closed service</span> | No weights. You rent access through an app or API, under terms the company can change. | Veo, Sora, Midjourney, Kling |
| <span class="tag open">open data</span> | The training data itself is public domain, openly licensed or contributed with consent. | CommonCanvas, Mitsua, Public Diffusion |

The Open Source Initiative published a formal [Open Source AI Definition](https://opensource.org/ai/open-source-ai-definition) in October 2024. Very few image or video models meet it in full, because almost none publish their training data. Keep that in mind when a company calls its model "open".

**Read the licence before you build on a model.** On Hugging Face it is in the model card's sidebar. Check three things: whether commercial use is allowed, whether your country is excluded, and whether the outputs carry conditions.

## Setting up a local studio

### Hardware, honestly

Local generation needs an **NVIDIA GPU**. VRAM (the graphics card's memory) decides what you can run:

- **6–8 GB:** Stable Diffusion 1.5 and SDXL, quantized versions of newer models, small video models at low resolution.
- **12–16 GB:** most current image models, LoRA training, the smaller video models.
- **24 GB and up:** the large video and 3D models at full quality.

These are rough brackets. Every model card lists its own requirements, and quantized versions (see below) move most models down a bracket.

Apple Silicon Macs can run many image workflows in ComfyUI, more slowly. If you have no suitable GPU, look for shared machines first: a school lab, a library, a community hacklab. Renting a cloud GPU by the hour is the next option. Each of these is a better habit than subscribing to a closed app.

### Install ComfyUI

[ComfyUI](https://www.comfy.org/) is an open-source (GPL-3.0), node-based interface for running diffusion models. Every part of a pipeline (model, text encoder, sampler, LoRA, ControlNet, VAE) is a node, and you wire nodes together into a workflow. It supports SD 1.5, SDXL, Flux, Z-Image, Wan, HunyuanVideo, LTX-Video, ControlNet, AnimateDiff and your own LoRAs. Thousands of community nodes add video, 3D, depth maps, segmentation and more.

1. Install the [desktop or portable version](https://www.comfy.org/download) for your system.
2. Install **ComfyUI-Manager**, the community tool for finding and installing custom nodes and models. Recent versions include it. If yours doesn't, open a terminal in `ComfyUI/custom_nodes` and run:
   ```
   git clone https://github.com/Comfy-Org/ComfyUI-Manager.git
   ```
   Restart ComfyUI and refresh the browser tab; a **Manager** button appears in the menu. (You need [Git](https://git-scm.com/downloads) installed. Check with `git --version`.)
3. Open the **Templates** menu and run the default text-to-image workflow. If an image appears, your studio works.

**Where models go.** Checkpoints go in `ComfyUI/models/checkpoints`, LoRAs in `models/loras`, ControlNets in `models/controlnet`, and so on. A red node almost always means a model is missing or in the wrong folder.

**On a shared or virtual GPU.** If ComfyUI crashes with memory-allocation errors on a virtual machine, add `--disable-cuda-malloc` to its launch command. Virtualized GPU drivers often reject the way PyTorch reserves memory.

### Running bigger models on smaller cards

- **Quantized models.** FP8 and GGUF versions shrink models to fit less VRAM with a small loss in quality. GGUF files load through the open-source [ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF) nodes (Apache 2.0).
- **Distilled "turbo" models** generate in 4–8 steps instead of 20–50. They use less time and less energy for each image.
- **Lower resolution first.** Find the composition small, then upscale only the images you keep.

## Learning resources

- [ComfyUI Course, Ep. 01](https://www.youtube.com/watch?v=HkoRkNLWQzY) by Pixaroma: a thorough free course, from installation onward. Pixaroma also publishes free starter workflows.
- [ComfyUI: Advanced Understanding](https://www.youtube.com/watch?v=_C7kR2TFIX0) by Latent Vision: how conditioning and sampling actually work.
- [Hugging Face courses](https://huggingface.co/learn): free courses on diffusion models and the open-source ML stack.
- [Comfy workflows](https://comfyworkflows.com/): workflows shared by the community.
