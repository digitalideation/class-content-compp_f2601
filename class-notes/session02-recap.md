---
title: "Week02 Recap"
description: "Recap of week02"
draft: false
tags:
  - class-notes
  - class
  - recap
---

# Creative AI – Session 2 Summary

## Session Structure

**Communication:** Slack (links pinned at top)  
**Content:** Course webpage (weekly blog post)  
**Tools:** GPU Hub (HSLU), JupyterHub, PyTorch  

### Focus of the Session

**Theme:** AI Image Generation

* Theoretical foundations
* Historical context
* Diffusion models
* CLIP model
* Hands-on experimentation (starting after break)

## Recap & Announcements

* All sessions are recorded and uploaded (same password for semester).
* Useful links (Zoom, webpage, tools) are pinned in Slack.
* GPU Hub access should be set up.
* VPN required when working off-campus.
* Weekly sharing of interesting AI examples encouraged.

Students shared:

* AI-generated Chinese New Year video (fully generated, including dialogue).
* Python-based sandbox game platform (code.org style remixable environment).

## Historical Evolution of AI Image Generation

### First Wave (~2015)

**DeepDream**

* Early neural AI art.
* Surreal, psychedelic imagery.

**StyleGAN**

* Face generation from scratch.
* ~28 million parameters.
* Could run locally on consumer GPUs.
* Specialized models (faces only, cars only, etc.).
* Example: “thispersondoesnotexist.com”

Technique used:
**GAN (Generative Adversarial Networks)**

### Second Wave (~2022 – Present)

Shift toward:

* Large-scale models
* Text-to-image systems
* General-purpose generation

Examples:

* DALL·E 2 (~3.5B parameters)
* Imagen (~4.6B parameters)

Closed-source, heavy infrastructure required.

### Stable Diffusion

Major breakthrough:

* ~890 million parameters
* Open-source
* Can run on consumer hardware
* Uses diffusion instead of GANs
* Introduced latent space encoding

Still part of the current generation paradigm.

## How Diffusion Models Work

### 1. Forward Diffusion (Training Phase)

Start with a real image (e.g., cat).

Gradually:

* Add noise
* Add more noise
* Continue until image becomes pure noise

Model learns:

“How much noise was added between each step?”

### 2. Reverse Diffusion (Generation Phase)

After training:

* Start from random noise.
* Gradually remove noise.
* Reconstruct structured image step by step.

Text prompts guide this denoising process.

Without guidance → random result.
With prompt (“a cat on a sofa”) → steered toward matching concept.

## Latent Space & Encoding

Directly operating on full-resolution images is computationally expensive.

Solution:

1. **Encoder**

   * Compress image into smaller representation.
   * Example: 512×512 image → 64×64 latent representation.

2. **Latent Space**

   * High-dimensional mathematical space.
   * Images exist as coordinates in this space.
   * Movement in this space changes features and concepts.

3. **Decoder**

   * Converts latent representation back to pixel image.

Key idea:
AI models work in compressed latent representations, not directly in pixels.

## Important Concepts Introduced

### Encoding / Decoding

Compressing and reconstructing information.

### Latent Space

High-dimensional space where representations exist and transformations occur.

### Guidance

Text prompts influence direction of denoising process.

### Scheduler / Sampler

Controls:

* Number of denoising steps
* Speed of noise removal
* Generation quality vs speed tradeoff

## CLIP Model

CLIP (by OpenAI, open-source):

* Compares text and images.
* Assigns similarity scores.
* Enables multimodal understanding.

Example:

Image of guacamole
→ High similarity to “a photo of guacamole”
→ Low similarity to unrelated labels.

CLIP enables text-guided image generation.

## Modalities

Different input/output combinations:

* Text → Image
* Image → Image
* Text + Image → Image
* Multimodal systems (e.g., ChatGPT)

## Conceptual Perspective

AI models are no longer “capsules” (faces only, cars only).

Modern models:

* Contain broad conceptual knowledge.
* Allow combination of ideas.
* Operate in vast latent conceptual spaces.

Key philosophical idea:

Perception depends on perspective.
Movement in latent space = change of viewpoint in conceptual space.

## Hands-On Setup

Students prepared:

* VPN (if off-campus)
* GPU Hub
* PyTorch environment
* Jupyter Notebook

### Tools Introduced

* PyTorch (ML framework by Meta)
* JupyterHub
* Course GitHub notebooks

First notebook loaded:

**01 – CLIP Intuition**

Next step (after break):

* Run CLIP model
* Experiment with text-image similarity
* Explore guidance mechanisms
* Prepare for diffusion experiments

## Learning Themes

* Understanding intuition over full mathematical depth.
* Technical literacy without needing full ML specialization.
* Exploration as inspiration for semester projects.
* Conceptual thinking about latent spaces and creative processes.

## For Next Session

* Review provided article on diffusion models.
* Explore image generation tools.
* Reflect on possible project ideas.
* Continue hands-on experimentation with diffusion and prompt guidance.
