---
title: Critical perspectives
module: "08"
description: Labour, consent, bias, copyright, concentration of power and environmental cost, with readings and talks.
prev: /modules/07-sound-and-voice.html
prev_title: Sound and voice
next: /modules/09-sustainable-practice.html
next_title: Sustainable practice
---

# Critical perspectives

<p class="lede">Learning these tools without learning their politics leaves an artist half-equipped. This module collects the readings, talks and facts the course discusses alongside the labs. They are offered as material for argument, not as settled conclusions.</p>

## Whose work is in the model?

- **Consent.** Read [AI and the Problem of Consent](https://artreview.com/ai-art-and-the-problem-of-consent/) (ArtReview, 2023) and Sarah Andersen, [The Alt-Right Manipulated My Comic. Then A.I. Claimed It](https://www.nytimes.com/2022/12/31/opinion/sarah-andersen-how-algorithim-took-my-work.html) (New York Times, 2022). Watch Steven Zapata, [The problem with AI-generated art](https://www.youtube.com/watch?v=exuogrLHyxQ) (TEDxBerkeley), and the [No AI Art protest on ArtStation](https://www.youtube.com/watch?v=QdVBiIpHh5w).
- **Data dignity.** Jaron Lanier argues that the people whose data trains these systems should have a stake in them: [A Blueprint for a Better Digital Society](https://hbr.org/2018/09/a-blueprint-for-a-better-digital-society) (Harvard Business Review, with E. Glen Weyl).
- **Hidden labour.** Datasets like ImageNet were labelled by crowd workers, and today's models depend on large numbers of low-paid annotators and content moderators. The "automation" is partly people.

## Copyright: where things stood in 2025

The law isn't settled, and it differs by country. Check for newer rulings before relying on any of this. The key US decision so far:

- In *Bartz v. Anthropic* (June 2025), Judge William Alsup ruled that training a model on legally acquired books can be fair use, but that downloading and keeping pirated copies is not. Anthropic then agreed to a proposed class settlement of at least $1.5 billion, about $3,000 per work.
- Dozens of other lawsuits against AI companies are still under way, and judges have weighed the fair-use factors differently.

If you train your own models: use legally obtained material, prefer public-domain, licensed or opt-in data, don't scrape sites that forbid it, and keep records of your sources ([module 02](02-data-and-consent.md)).

## Bias

Models reproduce the statistics of their data, including its stereotypes. Read Cade Metz, [We Teach A.I. Systems Everything, Including Our Biases](https://www.nytimes.com/2019/11/11/technology/artificial-intelligence-bias.html) (New York Times, 2019). Watch Sasha Luccioni, [AI Is Dangerous, but Not for the Reasons You Think](https://www.youtube.com/watch?v=eXdVDhOGqoE) (TED). She is a researcher at Hugging Face, and her talk ties bias, consent and climate together. A useful exercise: generate fifty "portraits of a CEO" or "a nurse" with a model, and look at who appears.

## Concentration

Training a frontier model costs more than all but a handful of companies can spend. The result is a few firms controlling both the models and the computing infrastructure they run on. Artist-facing tools get absorbed the same way: Weavy, a node-based AI workspace, was bought by Figma in October 2025 to become *Figma Weave*. Community infrastructure is the counterweight:
- [Hugging Face](https://huggingface.co/) hosts open models and datasets;
- [ComfyUI](https://www.comfy.org/) and its custom nodes are maintained in the open;
- grassroots research groups such as EleutherAI work outside the big labs;
- researchers publish their code and weights.

None of it is free of corporate money. Several open models in this toolkit come from Alibaba, Microsoft, Meta and Tencent. But it keeps the means of production inspectable and runnable by people outside those companies.

## Environmental cost

- The International Energy Agency estimates data centres used about **415 TWh of electricity in 2024, about 1.5% of global consumption**, and projects that this will more than double, to about **945 TWh by 2030**, driven largely by AI ([Energy and AI](https://www.iea.org/reports/energy-and-ai/executive-summary), 2025).
- Luccioni, Jernite and Strubell's study *Power Hungry Processing* (2023) measured 88 models on 10 tasks. **Image generation was the most energy-intensive task**, and the least efficient model they tested, Stable Diffusion XL, used **close to a full smartphone charge per image**. Smaller, task-specific models used a fraction of the energy of large general-purpose ones.

What that means in practice is in [module 09](09-sustainable-practice.md).

## Artists and essays

- Alan Warburton, [*The Wizard of AI*](https://alanwarburton.co.uk/) (2023): a video essay, made largely with generative tools, on what they do to artists.
- Holly Herndon and Mat Dryhurst: see [module 07](07-sound-and-voice.md).
- Kate Crawford, *Atlas of AI* (2021), and Kate Crawford and Vladan Joler, *Anatomy of an AI System* (2018): AI as extraction of minerals, labour and data.
- Emily M. Bender, Timnit Gebru, Angelina McMillan-Major and Margaret Mitchell, "On the Dangers of Stochastic Parrots" (2021): the paper on scale, cost and harm in large language models.

## Talks for discussion

These present opposing views, on purpose.

- [Debunking the great AI lie](https://www.youtube.com/watch?v=PBdZi_JtV4c): Noam Chomsky, Gary Marcus and Jeremy Kahn (Web Summit), sceptical of claims about understanding.
- [AI and the future of humanity](https://www.youtube.com/watch?v=LWiM-LuRe6w): Yuval Noah Harari (Frontiers Forum), on risk and power.
- [Is consciousness an illusion?](https://www.youtube.com/watch?v=BjmPvovl-V4) (Big Think): five experts on consciousness, as background for claims about "intelligent" machines.
