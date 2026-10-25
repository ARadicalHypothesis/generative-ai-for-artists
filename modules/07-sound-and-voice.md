---
title: Sound and voice
module: "07"
description: Open models for music, sound and speech, and voice as a question of consent.
prev: /modules/06-3d-and-space.html
prev_title: 3D and space
next: /modules/08-critical-perspectives.html
next_title: Critical perspectives
---

# Sound and voice

<p class="lede">Audio models are smaller and cheaper to run than video, which makes them a good place to work locally. Voice also makes the consent question personal: a cloned voice is someone's body.</p>

## Music and sound

| Model | What it does | Licence |
|---|---|---|
| [AudioCraft](https://github.com/facebookresearch/audiocraft): MusicGen and AudioGen (Meta) | Music and sound effects from text; MusicGen can follow a melody | <span class="tag weights">code MIT; weights CC BY-NC 4.0 (non-commercial)</span> |
| [Stable Audio Open](https://github.com/Stability-AI/stable-audio-tools) (Stability AI) | Short sounds, textures and loops; trained on Freesound and Free Music Archive material | <span class="tag weights">tools MIT; weights under Stability's community licence</span> |
| [AudioLDM](https://audioldm.github.io/) | Text-to-audio diffusion | <span class="tag weights">weights CC BY-NC-SA 4.0</span> |
| Riffusion | Stable Diffusion fine-tuned on spectrograms, turned into audio; an early, playful hack | <span class="tag weights">original model OpenRAIL-M</span> |
| Google MusicLM, Suno, Udio | Closed text-to-music systems and services | <span class="tag closed">closed</span> |

Try MusicGen in your browser on its [Hugging Face Space](https://huggingface.co/spaces/facebook/MusicGen) before installing anything.

## Speech

| Model | What it does | Licence |
|---|---|---|
| [Kokoro](https://huggingface.co/hexgrad/Kokoro-82M) | Small, fast text-to-speech that runs on a laptop | <span class="tag open">Apache 2.0</span> |
| [F5-TTS](https://github.com/SWivid/F5-TTS) | Voice cloning from a short sample | <span class="tag weights">code MIT; weights CC BY-NC (trained on the "in-the-wild" Emilia dataset)</span> |
| ElevenLabs | Commercial voice generation and cloning | <span class="tag closed">service</span> |

**Clone only voices you have permission to use**, including your own. Voice cloning is the most direct way generative AI can impersonate a real person, and the easiest to misuse.

## Artist spotlight: Holly Herndon

Herndon and Mat Dryhurst have spent a decade on the question these tools raise. *Holly+* is a model of Herndon's voice that anyone can use, under a protocol that shares revenue. *The Call* (Serpentine, 2024) turned fifteen UK choirs' recordings into a training dataset governed by a data trust: the singers decide how their voices are used. Watch: [What if you could sing in your favorite musician's voice?](https://www.youtube.com/watch?v=5cbCYwgQkTE) (TED). Read: [Holly Herndon and Mat Dryhurst on data, training and art making](https://artbasel.com/stories/ai-holly-herndon-mat-dryhurst-data-training-art-making) (Art Basel).

## Exercise

**A soundtrack with provenance.** Score the video from [module 05](05-video-and-animation.md) using open models and sound you recorded yourself. List every source and its licence in the credits. Commercial use of most of these weights isn't allowed, so check before you show the work outside class.
