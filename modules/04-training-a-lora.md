---
title: Training a LoRA
module: "04"
description: Teaching a model your own style, character, object or world with a small add-on trained on your own images.
prev: /modules/03-images-in-comfyui.html
prev_title: Images in ComfyUI
next: /modules/05-video-and-animation.html
next_title: Video and animation
---

# Training a LoRA

<p class="lede">A LoRA (low-rank adaptation) is a small file, usually tens to a few hundred megabytes, that adjusts a big model without retraining it. It's the most practical way to make a model yours: trained on your own images, in an hour or two, on one GPU.</p>

Watch first: [LoRA explained simply](https://www.youtube.com/watch?v=lixMONUAjfs) (Wes Roth). It's about language models, but the idea is the same for images.

## Where to train

| Option | What it is | Notes |
|---|---|---|
| [kohya_ss / sd-scripts](https://github.com/kohya-ss/sd-scripts) | The reference open-source trainer for SD 1.5, SDXL and Flux | <span class="tag open">Apache 2.0</span>. Local; the most control; steeper setup |
| [AI Toolkit](https://github.com/ostris/ai-toolkit) by Ostris | Open-source trainer with a simple interface, popular for Flux-family and video LoRAs | <span class="tag open">MIT</span>. Local |
| Hosted trainers (Civitai, fal.ai and others) | Upload a zip, get a LoRA back | <span class="tag closed">service</span>. No GPU needed, but your images go to someone else's server under their terms. Read them first, especially for unpublished work or images of other people |

Train locally when you can. Your dataset is your work, and it should stay with you.

## SDXL or Flux-family?

The patch you're training is different because the brains are different.

- **SDXL** learns your subject as textures and shapes. Its LoRAs are great for styles and abstraction, train on a mid-range GPU, and fit a huge ecosystem.
- **Flux-family** models learn your subject as relationships between parts. Characters keep their 3D structure and anatomy far better, but the models are heavier, and they carry a "Flux look" that is hard to remove.

| | SDXL LoRA | Flux-family LoRA |
|---|---|---|
| Images | 40–100 for a style | 20–40 |
| Captions | Comma-separated tags | Natural sentences |
| Trigger | A unique token (`trtc`) | A phrase (`in the style of trtc`) |
| Rank (dim) | 16–32 | 32–64 |
| Cropping | Avoid; use aspect-ratio bucketing | Never crop; keep wide and tall images |
| Steps | about 1,500–2,000 | 1,500–2,000; past about 3,000 it "fries" |

## Captioning: describe what you want to stay variable

The rule that makes everything else make sense: **whatever you don't caption gets absorbed into the trigger word.**

### For a character

- Start every caption with a unique trigger (`ohwx`, or the character's name).
- **Caption** what should be changeable: background, lighting, clothing (if there are several outfits), expression, camera angle.
- **Don't caption** what defines the character: face, hair colour, eye colour, a signature outfit.
- Always tag expressions and camera angles (`smiling`, `close-up`, `from side`), or the character gets stuck with one face and one view.
- Skip quality tags like "masterpiece", unless you want them baked in.

### For a style or a world: reverse logic

Here you want the model to learn the *look* and ignore the *subjects*, so describe the content in detail and never the style.

- Image: a watercolour of a warrior holding a sword.
- Bad caption: `watercolor style, painting, art`. The model decides warriors and swords are part of the style.
- Good caption: `a warrior, giant sword, standing in a field, armor`. The only thing left unexplained is the brushwork and palette, so that becomes the style.

Vary the subjects so the style can apply to anything: landscapes, people, objects, animals. For a specific world, include wide shots (the room), medium shots (the furniture) and close-ups (the wall texture).

For Flux-family models, write sentences: *"A [trtc] illustration of a warrior holding a sword in a field."*

### For an object or concept: isolate the variable

If every photo of your sculpture is in the same studio, the studio becomes part of the concept. Vary the surroundings: close-ups on plain backgrounds, the object in use, on different surfaces and in different light, from unusual angles. Twenty to thirty images is usually right. A few clean white-background shots help the model learn the exact outline.

## Choosing the right iteration

Trainers save several versions ("epochs") along the way. Think of a cake:

- **Early epochs** are raw: generic, little likeness.
- **Middle epochs** are usually right: strong likeness, still flexible.
- **Late epochs** are burnt: harsh contrast, strange colours, poses that won't change. This is *overfitting*.

Compare the sample images. The best version is usually just before quality starts to degrade. If you can't tell, the second-to-last is the safest pick.

## Exercise

**Train one LoRA on your own work.** Choose a style, character, object or world. Assemble 20–40 images you made or have the right to use (see [module 02](02-data-and-consent.md)), write a datasheet, caption them following the rules above, and train locally. Test the epochs side by side, and show where the LoRA succeeds and where it breaks.
