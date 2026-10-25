---
title: Data and consent
module: "02"
description: Building datasets you have the right to use, and models trained on public-domain, open or opt-in material.
prev: /modules/01-how-it-works.html
prev_title: How these systems work
next: /modules/03-images-in-comfyui.html
next_title: Images in ComfyUI
---

# Data and consent

<p class="lede">Every generated image is downstream of a dataset. Choosing your data is the most consequential creative and ethical decision in this whole toolkit, and the one the commercial tools hide from you.</p>

## Where the big models came from

Stable Diffusion was trained on image–caption pairs from **LAION-5B**, a dataset of about five billion links scraped from the web through Common Crawl and released by LAION, a German non-profit. Nobody whose work appears in it was asked. In December 2023 the Stanford Internet Observatory found links to child sexual abuse material in the dataset. LAION withdrew it and, in August 2024, released **Re-LAION-5B** with 2,236 suspected links removed. Most closed commercial models don't disclose their training data at all, so the same questions can't even be asked of them.

That's the baseline we're working against. The alternatives below are smaller and less polished, and they are where the field could go.

## Models built on consented or public data

| Model | Trained on | Licence |
|---|---|---|
| [CommonCanvas](https://huggingface.co/common-canvas) | Creative Commons–licensed images (2023) | <span class="tag open">CC BY-SA 4.0</span> |
| [Mitsua Diffusion One / Mitsua Likes](https://huggingface.co/Mitsua) | Public-domain and CC0 images (largely museum open-access collections) plus material used with permission | <span class="tag weights">non-commercial</span> |
| [Public Diffusion](https://spawning.substack.com/p/a-fireside-chat-with-the-creators) by Spawning | Public-domain and CC0 images only; designed to be fine-tuned on datasets that artists own | announced in private beta, Dec 2024 |

None of these matches the commercial models' range. That's a fair trade to discuss in class. A model with a narrower, honest dataset produces a different aesthetic, and that difference can be part of the work.

## Artists working on the data question

- **Holly Herndon and Mat Dryhurst** treat training data as the real material of AI art. *Holly+* made Herndon's voice into a model that anyone can use, under a protocol for sharing revenue. They co-founded **Spawning**, which runs *Have I Been Trained* and a "Do Not Train" registry. In *The Call* (Serpentine, 2024), fifteen UK choirs recorded a dataset governed by a data trust. Watch: [Holly Herndon at TED](https://www.youtube.com/watch?v=5cbCYwgQkTE).
- **Sofia Crespo** trains models on her own curated images of natural forms. Watch: [Artificial Lifeforms](https://www.youtube.com/watch?v=1Qks8g7QfRs).
- **Mario Klingemann** has worked with GANs and his own datasets since the mid-2010s.

## Tools for artists who don't want to be training data

- [Have I Been Trained](https://haveibeentrained.com/) (Spawning): search LAION for your work and register opt-outs.
- [Glaze and Nightshade](https://nightshade.cs.uchicago.edu/) (The Glaze Project, University of Chicago): free tools that disrupt style mimicry (Glaze) and discourage unconsented training (Nightshade).

## Building your own dataset

Most of the time you will train small models, such as LoRAs (see [module 04](04-training-a-lora.md)), on images you made or have the right to use. That is the most interesting option anyway.

### Good sources

- **Your own work:** drawings, photographs, renders, scans, archives of past projects.
- **Open-access collections:** [The Met Open Access](https://www.metmuseum.org/hubs/open-access), [Smithsonian Open Access](https://www.si.edu/openaccess), [Europeana](https://www.europeana.eu/), [Wikimedia Commons](https://commons.wikimedia.org/) (check each file's licence), and the Austrian National Library's [ONB Labs](https://labs.onb.ac.at/en/).
- **Collaborations:** material contributed by people who agreed to it in writing.

Avoid bulk-scraping websites with browser extensions, even when it's technically easy. Many sites' terms forbid it, and you can't give an account of where the material came from.

### What makes a dataset work

Whatever the type, a good dataset has four qualities:

- **Consistency:** same medium, same lighting logic, same aesthetic.
- **Clarity:** high resolution, no compression artefacts, no text or watermarks.
- **Focus:** one subject per image, no clutter, no mixed styles.
- **Balance:** enough variation to generalise, enough consistency to learn.

| You're training | What it learns | Images | Do | Avoid |
|---|---|---|---|---|
| **A style** | Palette, brushwork, texture, medium, composition habits | 10–30 (SDXL: 40+) | Same medium and palette throughout; ideally your own portfolio | Mixed styles, moodboards, collages |
| **A character** | Face, proportions, hair, clothing, pose habits | 15–40 | Same face from many angles, poses and backgrounds; a 3D model rendered in many poses works well | Too many close-ups or identical poses, occluded faces |
| **An object or concept** | A specific object, design language or artefact | 20–60 | Clean backgrounds, multiple angles, consistent light | Busy scenes, mixed materials |
| **A world** | Mood, architecture, colour language, environmental logic | 30–80 | Same world rules, materials and palette; wide, medium and close shots | Images that only "sort of" belong |
| **A GAN** (e.g. StyleGAN) | The texture distribution of the whole set | 200+ | Same aspect ratio (square is ideal), 512–1024 px, clean compositions | Mixed geometry, 4K images, screenshots, text |

**Never train on** Pinterest moodboards, screenshots of screenshots, low-resolution images, images with text overlays, or AI-generated images from several different models. They add noise, and they repeat the provenance problem you were trying to avoid.

### Document it

Keep a short **datasheet** with every dataset: where each image came from, its licence or permission, the date, and what you removed and why. It takes ten minutes, it makes your work defensible, and it's the habit the industry most lacks.
