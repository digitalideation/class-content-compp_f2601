---
title: "Week05 Recap"
description: "Recap of week05"
draft: false
tags:
  - class-notes
  - class
  - recap
---

# Creative AI – Session 5 Summary

> Note: the first ~15 minutes of the recording are missing, so this recap begins from the point where the transcript starts.

## Session Structure

**Communication:** Slack  
**Content:** Course webpage (week 05 materials)  
**Tools:** Replicate, Jupyter Notebook, GPU Hub (HSLU), Hugging Face, open-source audio models

### Focus of the Session

**Theme:** AI Audio Generation

- Historical evolution of generative audio and music systems
- Difference between symbolic generation and raw waveform generation
- Text-to-speech (TTS) and voice cloning
- Music generation tools and workflows
- Project directions for the second half of the semester

## Recap & Announcements

- The instructor mentioned that more tools would be introduced over the coming weeks, especially tools useful for student projects.
- The second half of the semester will be more project-oriented and more open in terms of implementation.
- Jupyter notebooks are one possible format for experiments and documentation, but students are not required to use them.
- Other directions are possible as well, including:
  - JavaScript-based interfaces,
  - web-based interactions with models,
  - API-based workflows,
  - and more traditional code/media repositories.

## Semester Projects

A student asked for examples of what kind of projects are expected later in the semester.

### Main Guidance

The instructor explained that:

- project outputs change a lot from year to year because the technology evolves quickly,
- but conceptually the projects often revolve around similar themes:
  - experimentation,
  - tool-making,
  - creative applications,
  - documentation,
  - and combining technical systems with artistic or design ideas.

### Expected Project Structure

Projects should ideally include:

- a repository or organized working folder,
- source code where relevant,
- media assets,
- documentation,
- and some record of research and experimentation.

Jupyter notebooks were presented as one useful way to document process and explain experiments, but not as a strict requirement.

### Flexibility of Format

The instructor emphasized that the second half of the semester is open in format:

- a project can be notebook-based,
- web-based,
- JavaScript-based,
- model/API-based,
- or another structure that makes sense for the student’s idea.

## Weekly Content: Audio Generation

This week shifted from text generation toward another major area of generative AI:

**audio generation**

The week 05 course material included:

- historical background on generative music and audio,
- examples from art and design,
- technical notes on how modern systems work,
- and practical tools for generating speech and music.

## Historical Evolution of Audio Generation

The session began with a broad historical overview of generative music and audio.

### Early Generative Systems

The instructor referenced early examples going back to the **1950s**, including:

- the **Illiac Suite** (1956),
- early autonomous or algorithmic composition experiments,
- and composers such as **Iannis Xenakis**, who explored computational methods in music.

These examples were used to show that generative audio did not begin with current AI systems.

### Rule-Based to Machine Learning

A key historical shift was highlighted:

**Before:** systems often relied on hand-written rules and algorithmic composition  
**Now:** machine learning systems learn patterns and rules from data

This connects audio generation to the broader course theme of how AI changes creative workflows.

### Symbolic Generation

Earlier systems often worked with **symbolic representations**:

- note sequences,
- MIDI,
- Markov chains,
- structured event-based music representations.

This is similar to sequence generation in text: one element follows another according to learned or designed structure.

### Shift to Raw Audio

One of the central concepts of the session was the transition from:

- **symbolic generation**  
  to
- **raw waveform generation**

This means that instead of only generating note instructions or symbolic sequences, newer systems can generate the actual sound wave directly.

The instructor framed this as one of the major changes in modern audio AI.

## Important Historical Models and Systems

### WaveNet

WaveNet was presented as one of the important early deep learning systems for raw audio generation.

Key point:

- it was among the first research systems to generate convincing raw audio directly.

### Google Magenta

The instructor also mentioned **Google Magenta** as a framework and ecosystem for music and audio generation.

### Text-to-Speech (TTS)

The session then moved toward **text-to-speech**, where a model takes text as input and generates spoken audio.

This served as a bridge between historical developments and the practical exercises of the day.

### Holly Herndon

The artist **Holly Herndon** was discussed as an example of a practitioner who goes beyond prompt-based generation.

Important themes in her work:

- artistic collaboration with AI,
- building custom datasets,
- training with her own voice,
- and creating her own tools rather than only using ready-made systems.

She was presented as a useful reference for students interested in more critical or artistic uses of generative voice.

### Jukebox

The session also referenced **Jukebox** by OpenAI as one of the earlier systems to generate longer-form music from prompts.

It was described as part of the broader wave of transformer-based innovation in audio generation.

### Dadabots

The collective **Dadabots** was mentioned as another interesting example, especially for experimental and stylistically distinctive AI music generation.

## How Modern Audio Generation Works

The instructor described the current state of the art as more complex than simple next-token sequence generation.

### Not Just Like LLMs

Unlike large language models, which generate one token after another, modern audio systems often combine several stages.

A simplified breakdown was given:

1. **Planning / structure**
   - the model creates a sketch or structural idea of the song/audio

2. **Compact representation**
   - the model generates an intermediate encoded representation

3. **Rendering**
   - a model turns that structure into final audio

### Denoising-Based Rendering

A major point was that many modern systems render final audio through a process closer to **diffusion / denoising**:

- starting from noise,
- gradually shaping it into coherent audio,
- generating the sound as a whole rather than purely one symbolic step at a time.

### Main Technical Distinction

The session emphasized the difference between:

- **sequence generation**  
  and
- **raw audio generation**

This was presented as one of the main technical ideas students should take away from the theory section.

## Instructor Examples and Experience

The instructor shared some of his own past and professional work to show what kinds of project support he can offer.

### Earlier Music Generation Experiments

One example involved older experiments using:

- MIDI datasets,
- sequence models,
- and relatively small neural networks.

The purpose of showing this was not only to present past work, but to make an important point:

**small and simple systems can still produce meaningful results**

Students do not necessarily need huge models or large-scale infrastructure for a good project.

### MIDI Dataset Curation

The instructor described building a small system that:

- downloaded many MIDI files,
- organized them by style,
- and trained small models on style-specific subsets.

This reinforced the idea that symbolic generation can still be an accessible and productive approach.

### Automated Translation for Exhibition Content

A more recent professional example involved an automated multilingual audio pipeline for exhibition content at **Novartis in Basel**.

This system involved:

- speech/audio input,
- translation,
- timing adaptation,
- and output speech generation in multiple languages.

This was used to demonstrate a practical and less purely artistic application of text-to-speech and speech pipelines.

### Real-Time Conversational Companion

The instructor also described work on a real-time conversation system that combined:

- speech-to-text,
- large language model APIs,
- and text-to-speech.

This was presented as another example of an end-to-end multimodal audio pipeline.

## Practical Plan for the Session

The hands-on part of the class focused on three directions:

1. **Text-to-speech**
   - first on Replicate
   - then inside Jupyter notebooks on the Hub

2. **Music generation**
   - using open-source and commercial models

3. **Optional local model execution**
   - depending on time and student comfort

## Voice Cloning and TTS

Before the practical exercises, the instructor briefly noted that students could later read more about:

- text-to-speech,
- voice cloning,
- and the risks and implications of cloning voices.

## Focus on Kyutai

The instructor highlighted **Kyutai**, a French company, as an especially interesting group to follow.

### Why Kyutai Was Highlighted

- strong research team
- open-source models
- efficient speech/audio systems
- European company
- useful for real-time audio interaction

### Examples Mentioned

#### Pocket TTS

- compact and efficient
- can run on CPU
- suitable even for smaller devices

#### Moshi

- real-time dialogue system
- open-source components
- relevant for conversational audio interfaces

The instructor recommended following Kyutai and experimenting with their tools later, even if they were not fully set up during class.

## Working with Replicate

The practical workflow began with **Replicate**.

Students were asked to:

- log in,
- explore model collections,
- and focus especially on two sections:
  - **generate speech**
  - **generate music**

### Suggested TTS Models

The instructor recommended starting with models such as:

- **Inworld TTS**
- **Chatterbox Turbo**

These were presented as accessible starting points for trying speech generation and voice cloning.

### What Students Were Asked to Do

First:

- test models directly on Replicate,
- get comfortable with the interfaces,
- try different settings,
- and listen to the outputs.

Then:

- move to Jupyter notebooks on the Hub,
- and try integrating the same kinds of models programmatically.

Unlike the previous week, the instructor intentionally did not want to write all the code live.  
Instead, students were encouraged to rely on what they had already learned and work more independently.

## Discussion: Are TTS Models Easier to Run Locally?

A student asked whether TTS models are usually easier to run locally than LLMs or image models.

### Instructor’s Answer

In general: **yes**

Reasons given:

- TTS has existed in useful forms even before modern AI
- the main recent improvements are in:
  - expressiveness,
  - accent,
  - intonation,
  - timing,
  - naturalness

The instructor also noted that many TTS systems are:

- smaller,
- more optimized,
- and often able to run on CPUs or lower-end devices.

### Comparison by Parameters

The instructor contrasted TTS models with LLMs:

- some TTS models may have around **100 million parameters**
- while even “small” LLMs often have **billions** of parameters

So overall, high-quality TTS tends to be much lighter and more accessible on consumer hardware.

## Project Discussion: Combining Modules

A student proposed combining this course project with another module by building an AI agent related to **color palette generation**.

### Proposed Idea

The student described a system where:

- a user uploads an image or enters a text description,
- the system extracts or generates a color palette,
- outputs dominant colors,
- and optionally provides different color codings or representations.

### Instructor Feedback

The instructor strongly supported the idea.

Main points:

- combining two modules into one project is a great idea
- it is fully acceptable as long as the work is documented and developed properly
- the project can go in many different directions:
  - palette extraction,
  - theory-driven palette generation,
  - visual generation from palettes,
  - audio/visual translation,
  - interactive websites,
  - one-off experimental pieces,
  - autonomous systems running continuously

### Broader Advice

The instructor emphasized that students can choose their depth of focus:

- focus on the technical implementation,
- focus on color theory or design research,
- focus on the final media artifact,
- or focus on the platform/interface.

All of these are valid as long as the project is coherent and thoughtfully documented.

## Learning Themes

This session emphasized several broader themes:

- generative audio has a long history before current AI hype
- modern systems combine multiple stages rather than a single simple process
- text-to-speech is a practical and accessible area for experimentation
- smaller and more efficient models can still be powerful
- projects do not need to be locked into a single technical format
- creative AI work can connect artistic experimentation, design research, and applied systems

## For Next Session

- Continue exploring TTS and music generation models on Replicate
- Try integrating some of them into Jupyter notebooks on the Hub
- Read the course notes on:
  - history of audio generation
  - symbolic vs raw audio generation
  - voice cloning and its risks
- Start thinking more concretely about project direction
- Prepare to discuss possible project formats and development paths in more detail next week
