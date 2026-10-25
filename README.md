# Generative AI for Artists

**An open, critical toolkit for making art with generative AI**: open-source models, local workflows, data with consent, and an honest account of the costs.

**Website:** https://aradicalhypothesis.github.io/generative-ai-for-artists/

Created by [Mattia Casalegno](https://www.mattiacasalegno.net).

**Course history.** Developed from *AI for Artists*, a graduate course Mattia Casalegno has taught in the Department of Digital Arts at Pratt Institute since 2023 (most recently Spring 2026), and from the public Generative AI workshop series he led at Pratt in Fall 2024 (3D form, game design, animation). This open edition, published in October 2026, reorganises that material around open-source, locally run and accountable tools, and adds a critical frame on data, labour and energy.

## The position

1. **Open first.** Where an open-source tool or openly licensed model can do the job, learn that one. Closed services are studied as objects of critique and comparison, not as defaults.
2. **Local and accountable.** Run models on your own machine: you know what runs, your material stays with you, and you can see the energy it uses.
3. **Data with consent.** Favour models and datasets built from public-domain, openly licensed or opt-in material, and build your own from work you have the right to use.

## Modules

| # | Module | What it covers |
|---|---|---|
| 00 | [Start here](modules/00-start-here.md) | The position; what "open" means; setting up ComfyUI on your own GPU |
| 01 | [How these systems work](modules/01-how-it-works.md) | Training vs programming; GANs, diffusion, transformers, flow matching; a short history |
| 02 | [Data and consent](modules/02-data-and-consent.md) | LAION and its problems; public-domain and opt-in models; building and documenting your own datasets |
| 03 | [Images in ComfyUI](modules/03-images-in-comfyui.md) | Text-to-image, img2img, ControlNet, LoRAs, upscaling with open models |
| 04 | [Training a LoRA](modules/04-training-a-lora.md) | SDXL vs Flux-family, captioning, choosing epochs, open trainers |
| 05 | [Video and animation](modules/05-video-and-animation.md) | Wan 2.2, LTX, AnimateDiff, Time-to-Move, StreamDiffusion in TouchDesigner, open mocap; the closed platforms studied critically |
| 06 | [3D and space](modules/06-3d-and-space.md) | TRELLIS.2, TripoSR, Gaussian splatting with Brush and SuperSplat, territory clauses, "world models" |
| 07 | [Sound and voice](modules/07-sound-and-voice.md) | MusicGen, Stable Audio Open, Kokoro; voice and consent; Holly Herndon |
| 08 | [Critical perspectives](modules/08-critical-perspectives.md) | Consent, labour, bias, copyright, concentration, environmental cost |
| 09 | [Sustainable practice](modules/09-sustainable-practice.md) | Working habits that use less compute and leave a clear record |
| | [Projects](projects.md) | Seven exercises, a final project structure, documentation standards |
| | [Tools](tools.md) | Every tool by openness and licence, with open alternatives to closed services |

## Requirements

An NVIDIA GPU with at least 6–8 GB of VRAM for local image work (more for video and 3D), or access to a shared machine. Apple Silicon Macs can run many image workflows, more slowly. Everything else is free and open source.

## Related

- [TouchDesigner for Artists](https://github.com/ARadicalHypothesis/touchdesigner-for-artists): an open four-session TouchDesigner course, including hand tracking.
- [Tangible Feelings: EEG for the Arts](https://aradicalhypothesis.github.io/tangible-feelings/): a traveling workshop on brain–computer interfaces for artists (2011–2013).

## Licence

Text: [CC BY 4.0](LICENSE.md). Linked tools, models and media keep their own licences.

Suggested credit: *"Generative AI for Artists" by Mattia Casalegno, CC BY 4.0, github.com/ARadicalHypothesis/generative-ai-for-artists*
