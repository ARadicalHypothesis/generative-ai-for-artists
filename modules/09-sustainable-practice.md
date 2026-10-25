---
title: Sustainable practice
module: "09"
description: Practical habits for making generative work with less energy, less dependence and clearer provenance.
prev: /modules/08-critical-perspectives.html
prev_title: Critical perspectives
next: /projects.html
next_title: Projects
---

# Sustainable practice

<p class="lede">You can't opt out of the environmental cost of these systems by being careful. You can make it smaller, visible and deliberate. These are working habits, not rules.</p>

## Use less compute per idea

1. **Choose the smallest model that does the job.** Energy scales with model size. A task-specific model or a small LoRA on SD 1.5 can beat a giant general-purpose model for your purpose. Luccioni et al. found that large general models used many times the energy of small specialised ones on the same task ([module 08](08-critical-perspectives.md)).
2. **Prefer few-step models.** Distilled turbo models (Z-Image Turbo, FLUX.1 [schnell], LCM LoRAs) generate in 4–8 steps instead of 20–50.
3. **Quantize.** FP8 and GGUF versions need less memory and often less power.
4. **Sketch small, finish big.** Explore at low resolution and short duration, then upscale or extend only what you keep. This matters most for video: a clip is hundreds of images.
5. **Fix the seed and change one thing at a time.** Deliberate iteration beats pulling a slot-machine lever a hundred times. It's better practice and it uses less energy.
6. **Reuse.** Share workflows, LoRAs and datasets with your class or community so the same training isn't repeated over and over.

## Know what you are using

- **Measure.** Read your GPU's power draw while it generates (`nvidia-smi` shows it live), multiply by the time, and keep a rough energy log for one project. It changes how you work.
- **Compare models.** The [AI Energy Score](https://huggingface.github.io/AIEnergyScore/) project led by Hugging Face rates the energy efficiency of open models on standard tasks.
- **Local or cloud?** Local generation shows you the cost and keeps your data. Cloud services hide both. Where your electricity comes from matters too: a shared machine on a cleaner grid can beat a personal one.

## Depend on what you can keep

- **Archive your stack.** Save the exact model files, LoRAs, custom nodes and workflow JSON with each project. Closed services change and disappear, and your own copies are the only reliable record of how a work was made.
- **Share infrastructure.** Shared GPU rooms at schools, libraries and artist-run spaces put access in common hands and keep machines busy instead of idle.
- **Credit and document.** List models, datasets and licences in the credits of every work, the same way you'd credit a collaborator.

## A checklist for every project

- [ ] Smallest workable model chosen, and why
- [ ] Training data of every model checked (or noted as undisclosed)
- [ ] Licence read: commercial use, territory, conditions on outputs
- [ ] Your own datasets documented in a datasheet
- [ ] Explored at low resolution before final renders
- [ ] Rough energy estimate recorded
- [ ] Models, workflows and settings archived with the project
- [ ] Credits list models, datasets and licences
