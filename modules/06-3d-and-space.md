---
title: 3D and space
module: "06"
description: Image-to-3D, Gaussian splatting and texturing with open models, and a critical look at "world models".
prev: /modules/05-video-and-animation.html
prev_title: Video and animation
next: /modules/07-sound-and-voice.html
next_title: Sound and voice
---

# 3D and space

<p class="lede">Generative 3D moved in two years from blurry research demos to usable meshes. Some of the best models are open; some "free" ones carry licences that quietly exclude whole regions of the world.</p>

## Image and text to 3D

| Model | What it does | Licence |
|---|---|---|
| [TRELLIS.2](https://github.com/microsoft/TRELLIS.2) (Microsoft) | Image-to-3D with high-quality geometry and textures; runs in ComfyUI | <span class="tag open">MIT</span> (code and weights) |
| [TripoSR](https://github.com/VAST-AI-Research/TripoSR) / [TripoSF](https://github.com/VAST-AI-Research/TripoSF) (VAST and Stability AI) | Fast single-image reconstruction; TripoSF for high-resolution, complex shapes | <span class="tag open">MIT</span> |
| [DreamGaussian](https://github.com/dreamgaussian/dreamgaussian) | Text- or image-to-3D through Gaussian splats, converted to meshes | <span class="tag open">MIT</span> |
| [Hunyuan3D 2.1](https://github.com/Tencent-Hunyuan/Hunyuan3D-2.1) (Tencent) | Strong image-to-3D with PBR textures | <span class="tag weights">Tencent community licence: not licensed in the EU, UK or South Korea; companies with more than 1M monthly users need a separate licence</span> |
| [SAM 3D Objects](https://github.com/facebookresearch/sam-3d-objects) (Meta) | Reconstructs objects from a single photo | <span class="tag weights">Meta's own licence; gated, access by request</span> |
| Meshy, Tripo (app), Rodin, CSM, Masterpiece X | Commercial text- and image-to-3D apps | <span class="tag closed">service</span> |

**Read the territory clause.** The Hunyuan licence states that it "does not apply in the European Union, United Kingdom and South Korea." A tool can be free to download and still not be legally yours to use where you live.

Watch: [ComfyUI TRELLIS.2](https://www.youtube.com/watch?v=KUNLitkYdwM) and [Free AI texture workflow (TRELLIS.2 + Modddif)](https://www.youtube.com/watch?v=sC5Can0HJo8) (PixelArtistry) · [Tripo AI is now open source](https://www.youtube.com/watch?v=kYB7N9HSzwA) (askNK) · [AI retopology and UV](https://www.youtube.com/watch?v=ltzhkJP-43E) (Stefan 3D AI).

**Generated meshes need work.** Expect messy topology. Plan time for retopology, UVs and rigging in [Blender](https://www.blender.org/) (open source) before an asset is usable in a game engine or for fabrication.

## Capturing the real: Gaussian splatting

Gaussian splatting reconstructs a scene from photos or video as millions of soft, coloured points. It's fast to train and photoreal to view, a successor to photogrammetry and NeRFs. Watch: [What is 3D Gaussian Splatting?](https://www.youtube.com/watch?v=Tnij_xHEnXc) (Bad Decisions Studio) · [3D Gaussian Splatting, explained](https://www.youtube.com/watch?v=sQcrZHvrEnU) (Bilawal Sidhu).

| Tool | Role | Licence |
|---|---|---|
| [Brush](https://github.com/ArthurBrussee/brush) | Trains splats on your own machine, on most GPUs | <span class="tag open">Apache 2.0</span> |
| [gsplat](https://github.com/nerfstudio-project/gsplat) (Nerfstudio) | Open-source splatting library | <span class="tag open">Apache 2.0</span> |
| [SuperSplat](https://github.com/playcanvas/supersplat) (PlayCanvas) | Browser-based editor for cleaning, cropping and publishing splats | <span class="tag open">MIT</span> |
| [Original 3DGS code](https://github.com/graphdeco-inria/gaussian-splatting) (Inria) | The research implementation | <span class="tag weights">research / non-commercial licence</span> |
| Polycam, Luma, Postshot | Capture and processing apps | <span class="tag closed">proprietary</span> |

## Texturing with diffusion

- [Dream Textures](https://github.com/carson-katri/dream-textures) (GPL-3.0): generate textures and render passes inside Blender.
- [StableProjectorz](https://stableprojectorz.com/) (free): project diffusion-generated textures onto models from multiple views. Watch: [Texturing the dungeon platform](https://www.youtube.com/watch?v=j6Qb3FsWIEA) (Igor Aherne).

## "World models"

World Labs' **Marble** generates explorable 3D environments from images and text, and Google DeepMind's **Genie 3** generates interactive worlds in real time. Both arrive with big claims about "spatial intelligence". Read Fei-Fei Li's [From Words to Worlds](https://drfeifei.substack.com/p/from-words-to-worlds-spatial-intelligence), then ask the questions from [module 01](01-how-it-works.md): what were these trained on, who can run them, and what kind of world do they make easy to imagine? Marble exports Gaussian splats, which can be opened and edited in the open tools above.

## Exercise

**An asset you could fabricate or place.** Make a small series of 3D objects, or one character, with an open model (TRELLIS.2 or TripoSR, locally), or capture a real object or place as a Gaussian splat with Brush. Clean it in Blender or SuperSplat. Document the full pipeline: input, model, settings, clean-up. Note where the model's guesses replaced information it didn't have.
