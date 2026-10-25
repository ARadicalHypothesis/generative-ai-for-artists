---
title: Tools
description: Every tool in the course, sorted by how open it is, with licences and open alternatives to the closed services.
---

# Tools

<p class="lede">Every tool the course touches, sorted by how open it is. Licences are taken from each project's GitHub repository or Hugging Face model card, checked in October 2026. Licences change, so verify before you depend on one.</p>

<span class="tag open">open source</span> code (and weights, for models) under a standard open licence · <span class="tag weights">open weights, restricted</span> downloadable, with limits on use · <span class="tag closed">closed</span> rented access only

## Open alternatives to closed services

| If the course mentions… | It's… | Try instead |
|---|---|---|
| Midjourney, Nano Banana, DALL·E | <span class="tag closed">closed</span> image services | Z-Image Turbo, FLUX.1 [schnell], SDXL or Qwen-Image in ComfyUI, with your own LoRAs ([03](modules/03-images-in-comfyui.md)) |
| Veo 3.1 / Flow, Sora 2, Kling 3.0, Runway, Pika | <span class="tag closed">closed</span> video services | Wan 2.2, LTX-Video, AnimateDiff; Time-to-Move for directed motion ([05](modules/05-video-and-animation.md)) |
| Weavy (Figma Weave), Flora, Krea | <span class="tag closed">closed</span> node or canvas workspaces | ComfyUI, InvokeAI |
| fal.ai, Replicate | <span class="tag closed">rented</span> GPU infrastructure | Your own GPU, or a shared school or community machine |
| Civitai and fal.ai LoRA trainers | <span class="tag closed">hosted</span> training | kohya_ss / sd-scripts, AI Toolkit ([04](modules/04-training-a-lora.md)) |
| Meshy, Tripo (app), Rodin, CSM, Masterpiece X | <span class="tag closed">closed</span> 3D services | TRELLIS.2, TripoSR / TripoSF, DreamGaussian ([06](modules/06-3d-and-space.md)) |
| Polycam, Luma, Postshot | <span class="tag closed">proprietary</span> capture | Brush, gsplat, SuperSplat |
| Move.ai, Plask, Cascadeur, Mootion | <span class="tag closed">proprietary</span> motion | FreeMoCap, MDM, Blender retargeting |
| ElevenLabs | <span class="tag closed">closed</span> voice | Kokoro; F5-TTS for non-commercial work ([07](modules/07-sound-and-voice.md)) |
| Suno, Udio, MusicLM | <span class="tag closed">closed</span> music | MusicGen, Stable Audio Open (both non-commercial) |
| Magnific, Topaz | <span class="tag closed">closed</span> upscalers | Real-ESRGAN in ComfyUI |
| ChatGPT custom GPTs | <span class="tag closed">closed</span> language model | An open-weight language model run locally with llama.cpp or Ollama |

## Interfaces and infrastructure

| Tool | Licence |
|---|---|
| [ComfyUI](https://github.com/Comfy-Org/ComfyUI) | <span class="tag open">GPL-3.0</span> |
| [ComfyUI-Manager](https://github.com/Comfy-Org/ComfyUI-Manager) | <span class="tag open">GPL-3.0</span> |
| [ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF) | <span class="tag open">Apache 2.0</span> |
| [InvokeAI](https://github.com/invoke-ai/InvokeAI) | <span class="tag open">Apache 2.0</span> |
| [Diffusers](https://github.com/huggingface/diffusers) (Hugging Face) | <span class="tag open">Apache 2.0</span> |
| [ControlNet](https://github.com/lllyasviel/ControlNet) | <span class="tag open">Apache 2.0</span> |
| [kohya_ss / sd-scripts](https://github.com/kohya-ss/sd-scripts) | <span class="tag open">Apache 2.0</span> |
| [AI Toolkit](https://github.com/ostris/ai-toolkit) | <span class="tag open">MIT</span> |
| [Google Colab](https://colab.research.google.com/) | <span class="tag closed">hosted notebooks</span>: free tier, Google account required |

## Image models

| Model | Licence |
|---|---|
| Z-Image Turbo (Tongyi-MAI) | <span class="tag open">Apache 2.0</span> |
| FLUX.1 [schnell], FLUX.2 [klein] 4B (Black Forest Labs) | <span class="tag open">Apache 2.0</span> |
| Qwen-Image (Alibaba) | <span class="tag open">Apache 2.0</span> |
| CommonCanvas | <span class="tag open">CC BY-SA 4.0</span> |
| Stable Diffusion 1.5 | <span class="tag weights">CreativeML OpenRAIL-M</span> |
| SDXL | <span class="tag weights">OpenRAIL++</span> |
| SD 3.5 | <span class="tag weights">Stability community licence</span> |
| FLUX.1 [dev] | <span class="tag weights">non-commercial</span> |
| Mitsua Likes | <span class="tag weights">non-commercial</span> |
| [Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN) (upscaler) | <span class="tag open">BSD-3-Clause</span> |

## Video and motion

| Model / tool | Licence |
|---|---|
| [Wan 2.2](https://github.com/Wan-Video/Wan2.2) | <span class="tag open">Apache 2.0</span> |
| [AnimateDiff](https://github.com/guoyww/AnimateDiff) | <span class="tag open">Apache 2.0</span> |
| [StreamDiffusion](https://github.com/cumulo-autumn/StreamDiffusion) | <span class="tag open">Apache 2.0</span> |
| [Time-to-Move](https://github.com/time-to-move/TTM) | <span class="tag open">Apache 2.0</span> |
| [ComfyUI-WanVideoWrapper](https://github.com/kijai/ComfyUI-WanVideoWrapper) | <span class="tag open">Apache 2.0</span> |
| [MagicAnimate](https://github.com/magic-research/magic-animate) | <span class="tag open">BSD-3-Clause</span> |
| [MDM](https://github.com/GuyTevet/motion-diffusion-model) | <span class="tag open">MIT</span> |
| [FreeMoCap](https://github.com/freemocap/freemocap) | <span class="tag open">AGPL-3.0</span> |
| [LTX-Video](https://github.com/Lightricks/LTX-Video) | <span class="tag weights">code Apache 2.0; weights Lightricks licence</span> |
| [HunyuanVideo](https://github.com/Tencent-Hunyuan/HunyuanVideo) | <span class="tag weights">Tencent community licence; excludes EU, UK, South Korea</span> |
| Stable Video Diffusion | <span class="tag weights">Stability community licence</span> |
| Deforum | see [repository](https://github.com/deforum/sd-webui-deforum) |
| StreamDiffusionTD (DotSimulate) | TouchDesigner component, distributed by its author |

## 3D

| Model / tool | Licence |
|---|---|
| [TRELLIS.2](https://github.com/microsoft/TRELLIS.2) | <span class="tag open">MIT</span> |
| [TripoSR](https://github.com/VAST-AI-Research/TripoSR), [TripoSF](https://github.com/VAST-AI-Research/TripoSF) | <span class="tag open">MIT</span> |
| [DreamGaussian](https://github.com/dreamgaussian/dreamgaussian) | <span class="tag open">MIT</span> |
| [Brush](https://github.com/ArthurBrussee/brush) | <span class="tag open">Apache 2.0</span> |
| [gsplat](https://github.com/nerfstudio-project/gsplat) | <span class="tag open">Apache 2.0</span> |
| [SuperSplat](https://github.com/playcanvas/supersplat) | <span class="tag open">MIT</span> |
| [Dream Textures](https://github.com/carson-katri/dream-textures) | <span class="tag open">GPL-3.0</span> |
| [Stable DreamFusion](https://github.com/ashawkey/stable-dreamfusion) | <span class="tag open">Apache 2.0</span> |
| [Stable Diffusion Tools for Unreal](https://github.com/Mystfit/Unreal-StableDiffusionTools) | <span class="tag open">MIT</span> |
| [Hunyuan3D 2.1](https://github.com/Tencent-Hunyuan/Hunyuan3D-2.1) | <span class="tag weights">Tencent community licence; excludes EU, UK, South Korea</span> |
| [SAM 3D Objects](https://github.com/facebookresearch/sam-3d-objects) | <span class="tag weights">Meta licence; gated</span> |
| [Original 3D Gaussian Splatting](https://github.com/graphdeco-inria/gaussian-splatting) | <span class="tag weights">research / non-commercial</span> |
| [Instant-NGP](https://github.com/NVlabs/instant-ngp) (NVIDIA) | <span class="tag weights">NVIDIA non-commercial licence</span> |

## Sound and voice

| Model / tool | Licence |
|---|---|
| [Kokoro](https://huggingface.co/hexgrad/Kokoro-82M) | <span class="tag open">Apache 2.0</span> |
| [AudioCraft](https://github.com/facebookresearch/audiocraft) (MusicGen, AudioGen) | <span class="tag weights">code MIT; weights CC BY-NC 4.0</span> |
| [Stable Audio Open](https://github.com/Stability-AI/stable-audio-tools) | <span class="tag weights">tools MIT; weights Stability community licence</span> |
| [AudioLDM](https://audioldm.github.io/) | <span class="tag weights">weights CC BY-NC-SA 4.0</span> |
| [F5-TTS](https://github.com/SWivid/F5-TTS) | <span class="tag weights">code MIT; weights CC BY-NC</span> |

## Communities and learning

- [Hugging Face](https://huggingface.co/): open models, datasets and Spaces you can try in the browser, plus free [courses](https://huggingface.co/learn).
- [Comfy workflows](https://comfyworkflows.com/): workflows shared by the community.
- [Pixaroma](https://www.youtube.com/@pixaroma): free ComfyUI courses and workflows.
- [Theoretically Media](https://www.youtube.com/@TheoreticallyMedia): news on generative video. It mostly covers commercial tools, so watch with the alternatives table above in mind.
