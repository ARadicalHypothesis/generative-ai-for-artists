---
title: How these systems work
module: "01"
description: Programming versus training, and the main families of generative models, explained for artists.
prev: /modules/00-start-here.html
prev_title: Start here
next: /modules/02-data-and-consent.html
next_title: Data and consent
---

# How these systems work

<p class="lede">You don't need the maths to make good work with these tools. You do need an accurate picture of what they are, because the picture shapes what you ask of them, and what you believe about them.</p>

## Programming versus training

A conventional program is a set of rules someone wrote. A machine-learning model is a file of numbers produced by *training*: an algorithm shown a large set of examples adjusts millions or billions of internal values until it reproduces the patterns in those examples. You never write the rules. You choose the data and the training procedure, and the rules emerge from them.

Two consequences matter for artists:

- **A model is its data.** Its sense of what a "portrait" or a "forest" looks like is a statistical summary of the images it was shown. Whatever those images over- or under-represent, the model will too.
- **A model predicts. It doesn't understand.** It produces what is probable given its training, which is why outputs drift toward the average and why rare subjects come out wrong.

Watch: [Machine Learning Explained Simply](https://www.youtube.com/watch?v=Au1OxVSyGas) (The Gradient Descent) · [What Is AI?](https://www.youtube.com/watch?v=NbEbs6I3eLw) (Museum of Science)

## The model families

| Family | How it generates | Where you meet it |
|---|---|---|
| **GANs** (generative adversarial networks, 2014) | Two networks compete: one generates, one judges real from fake, until the fakes pass. | StyleGAN, early AI art, latent-space walks |
| **CNNs** (convolutional neural networks) | Scan an image in small patches to learn edges, textures and shapes. | Inside SDXL's U-Net; image recognition |
| **Diffusion models** | Learn to remove noise step by step. Generation starts from pure noise and "denoises" toward an image that matches the prompt. | Stable Diffusion, SDXL, most video models |
| **Transformers** | Use *attention* to relate every part of a sequence to every other part: words in a sentence, or patches of an image. | Language models; Flux and other new image models |
| **Flow matching** | A newer training method that learns a direct path from noise to image, so fewer steps are needed. | Flux, Z-Image, Wan |
| **3D representations** (NeRFs, Gaussian splats, meshes) | Learn a scene or object as a volume, a cloud of soft points, or a surface. | Photogrammetry successors, text- and image-to-3D |

Most current tools combine these. An image model typically uses a transformer-based text encoder to read the prompt, a diffusion or flow model to generate, and a VAE to turn the result into pixels.

Watch:
- [How AI Image Generators Work](https://www.youtube.com/watch?v=1CIpzeNxIhU) (Computerphile)
- [Diffusion models explained in 4 difficulty levels](https://www.youtube.com/watch?v=yTAMrHVG1ew) (AssemblyAI)
- [What are GANs?](https://www.youtube.com/watch?v=TpMIssRdhco), [What are CNNs?](https://www.youtube.com/watch?v=QzY57FaENXg) and [What are Transformers?](https://www.youtube.com/watch?v=ZXiruGOCn9s) (IBM Technology)
- [Convolutional Network Demo from 1989](https://www.youtube.com/watch?v=FwFduRA_L6Q): Yann LeCun's handwriting-recognition demo, a useful reminder of how long these ideas have been around.

## A short history, with the winters left in

- **1943:** McCulloch and Pitts publish the first mathematical model of a neuron.
- **1956:** The Dartmouth workshop names the field "artificial intelligence".
- **1958:** Frank Rosenblatt's perceptron, an early learning machine.
- **1970s and late 1980s:** two "AI winters", when funding and interest collapsed after inflated promises.
- **1986:** Rumelhart, Hinton and Williams popularise backpropagation, the method still used to train neural networks.
- **2009:** ImageNet, a dataset of millions of labelled photos, many labelled by low-paid crowd workers.
- **2012:** AlexNet wins ImageNet on GPUs, and deep learning takes off.
- **2014:** GANs.
- **2017:** the transformer ("Attention Is All You Need").
- **2020–22:** diffusion models overtake GANs; DALL·E 2, Midjourney and Stable Diffusion reach the public. Stable Diffusion's release as downloadable weights in 2022 is what made local, artist-controlled generation possible.

Two patterns are worth noticing. Each wave arrived with predictions that it would replace human work within a few years. And each depended on large datasets assembled from other people's labour and images.

## Agents and "world models"

The industry's current claims centre on **agents** (systems that plan and act through software on your behalf) and **world models** (systems that generate explorable 3D environments, such as Google DeepMind's Genie 3 or World Labs' Marble). Treat both as research directions and marketing at the same time. Ask what data they were trained on, who can run them, and who decides what they are for.

Watch: [Generative vs Agentic AI](https://www.youtube.com/watch?v=EDb37y_MhRw) (IBM Technology) · [Genie 3](https://www.youtube.com/watch?v=PDKhUknuQDg) (Google DeepMind's own announcement, so read it critically)
