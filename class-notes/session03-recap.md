---
title: "Week03 Recap"
description: "Recap of week03"
draft: false
tags:
  - class-notes
  - class
  - recap
---

# Creative AI – Session 3 Summary

## Session Structure

**Communication:** Slack (links and weekly recaps pinned at top)  
**Content:** Course webpage (weekly session page + notes)  
**Tools:** NotebookLM, GPU Hub (HSLU), Jupyter Notebook, GPT4All, Hugging Face Transformers

### Focus of the Session

**Theme:** AI Text Generation

- How large language models (LLMs) are trained
- Difference between base models and assistants
- Prompting, personas, and system prompts
- Retrieval and retrieval-augmented generation (RAG)
- Hands-on experimentation with local language models in notebooks

## Recap & Announcements

- The previous session recap, content, and recording were posted on Slack.
- Image generation will return next week with more experiments.
- Next week will shift toward the **creative process** and a new platform that is simpler than Jupyter notebooks and easier to integrate with websites and other tools.
- Useful course resources remain pinned in Slack.
- The teacher mentioned wanting more space for sharing AI examples, design references, and experiments seen by students during the week.

## Course Direction

The instructor emphasized that the course is currently building **foundations**:

- understanding the basic concepts behind generative AI,
- learning how the systems work,
- and preparing to combine these ideas later into more creative workflows.

The idea is to first build conceptual and technical literacy, then later assemble these elements into more open-ended creative processes.

## Weekly Content: Text Generation

This week focused on another major branch of generative AI:

**Text generation with large language models**

The session was divided into **two main parts**:

### Part 1 — How LLMs Are Built

Goals:

- Understand how LLM training works
- Explain the overall training pipeline
- Understand the difference between a **base model** and an **assistant**
- Identify common failures and limitations
- Build intuition for how LLM-based workflows operate

### Part 2 — How LLMs Are Used

Goals:

- Work directly with language models in notebooks
- Test prompting and system instructions
- Explore personas and prompt control
- Understand retrieval and conversational memory
- Build practical intuition through experimentation

## Part 1: NotebookLM as Learning Tool

Instead of going through dry slides remotely, the instructor proposed using **NotebookLM** by Google for the theory section.

### Why NotebookLM?

It was presented as a way to:

- aggregate multiple learning sources,
- discuss and query them through an assistant,
- generate summaries in a simplified way,
- and support self-study through extra features.

### Material Included in the NotebookLM

The prepared notebook included sources such as:

- videos,
- webpages,
- explanations of GPT and transformers,
- and other background material related to LLM training.

### Suggested Learning Flow

Students were encouraged to spend around **20–30 minutes** exploring the NotebookLM before continuing the recording.

Recommended sequence:

1. Watch the short explanation video on how LLMs work and are trained.
2. Listen to the generated podcast conversation.
3. Use the quiz and flashcards to reinforce key concepts.
4. Ask questions directly in NotebookLM.

### Important Framing

The NotebookLM material was intentionally designed for a **non-specialist audience**:

- simpler explanations,
- guided analogies,
- and a focus on conceptual understanding rather than mathematical depth.

## Part 2: Jupyter Notebooks and Practical Experiments

After the theory section, the session moved back to **Jupyter notebooks** on the GPU Hub.

### Setup Reminders

Students were reminded to:

- connect to VPN if working from home,
- log into the GPU Hub,
- launch a PyTorch environment,
- and access the class notebook repository.

### New Workflow for Opening Notebooks

Instead of opening notebooks by URL, the instructor introduced a new workflow:

- use the terminal inside Jupyter,
- clone the class repository from GitHub,
- and retrieve only the relevant folder.

This was presented as a cleaner and more flexible setup.

## Notebook 1: Basic LLM Interaction, Personas, and Prompt Contracts

The first practical notebook introduced basic interaction with a local language model using **GPT4All**.

### Tool Introduced: GPT4All

GPT4All was described as:

- a small open-source tool,
- made by **Nomic**,
- usable as both a desktop interface and a Python library,
- and suitable for running smaller models locally.

The class used it as a **Python library** inside the notebook.

### Models

Students loaded a small local model (Hermes / Nous-based model) and were reminded that:

- model size is measured in **billions of parameters**,
- the models used here are considered **small** compared to frontier systems,
- yet they are still surprisingly capable.

Quantization was also mentioned as a way of compressing models to make them lighter and more practical.

### First Experiment: Raw Prompting

A simple prompt was sent to the model:

- asking for project ideas for first-year design students using AI text tools.

This demonstrated the most basic LLM workflow:

1. send a prompt,
2. receive generated text,
3. inspect the answer.

The result was described as functional but generic.

### System Prompts and Personas

The next step introduced **system prompts**, which define the role or behavior of the assistant before the conversation begins.

Example persona:

- “You are a patient teacher. Explain clearly with simple language.”

This showed how the same underlying model can produce different styles of response depending on the framing.

### Key Concept: System Prompt

A major takeaway:

- a model can be strongly shaped by the instructions it receives,
- not necessarily by changing what it knows,
- but by changing **how it answers**.

Examples mentioned included making a model speak like:

- a teacher,
- a pirate,
- or a technical expert.

### Prompt Contracts

The session then introduced a more structured version of prompting called a **prompt contract**.

This included specifying:

- role,
- audience,
- constraints,
- output format.

Instead of only giving a loose persona, the user defines a more explicit framework the model should follow.

### Main Insight from Notebook 1

The stronger and more structured the prompt, the more controlled and precise the response becomes.

The notebook showed three stages:

- baseline prompt,
- persona-based prompt,
- prompt contract.

This progression illustrated how prompt design shapes output quality and tone.

## Notebook 2: Retrieval and RAG

The second notebook focused on **retrieval** and **retrieval-augmented generation (RAG)**.

### What Retrieval Means

The instructor explained retrieval in simple terms:

When a user uploads a document to a language model, the system does not simply do a naive full-text keyword search.  
Instead, it uses retrieval methods to find the most relevant chunks of information.

### RAG = Retrieval + Augmentation + Generation

This three-step structure was emphasized clearly:

1. **Retrieval**  
   Find the relevant content.

2. **Augmentation**  
   Insert that content into the prompt as context.

3. **Generation**  
   Let the language model produce the answer based on that context.

### Simple Proof of Concept

A small example was used:

- a short fact like “the Green Campus meeting is Friday at 3pm and pizza will be served,”
- then a question such as:
  - “When is the meeting and what food is served?”

The model was instructed to answer **only using the provided context**.

This demonstrated that the model can answer accurately when the needed information is embedded in the prompt.

### From Simple Context to Multiple Chunks

The next step expanded from one sentence to multiple text chunks.

Now the problem became:

- how to automatically retrieve the right pieces of text from a larger set.

### Embeddings

This introduced the concept of **embeddings**:

- text is converted into vectors,
- these vectors become positions in a high-dimensional space,
- and similarity can be measured mathematically.

Instead of only searching keywords, the system compares **meaning**.

### Why Embeddings Matter

Embeddings allow the system to:

- identify semantically related text,
- retrieve relevant chunks,
- and support document question-answering more effectively than plain text matching.

### Building the Full Pipeline

The notebook then combined everything:

- retrieve the most relevant chunks,
- build a context block,
- pass it into the prompt,
- and generate an answer.

This recreated the basic logic of modern RAG systems in a simple and transparent way.

### Personas + Retrieval

The notebook also combined retrieval with earlier persona work.

The same retrieved content could be presented by different assistant roles:

- tutor,
- admin,
- coach.

This showed that retrieval provides the facts, while the system prompt shapes the voice and style of the answer.

## Multi-Turn Conversation and Context

The notebook ended by showing how **conversation history** affects model behavior.

### Important Concept: Multi-Turn Chat

In a real assistant:

- the conversation is not one isolated question,
- each new message is appended to the existing exchange,
- and the whole conversation influences later replies.

### Main Insight

The model is always working with accumulated context.

This explains why:

- early prompts can work very well,
- but long conversations may degrade over time,
- because too much information builds up and affects performance.

This was used to introduce the idea of **context windows** and why conversation structure matters.

## Notebook 3: Understanding Embeddings More Directly

The third notebook focused more explicitly on what embeddings look like and how they work.

### What the Notebook Showed

Students worked with a small text corpus related to design and AI, then:

- embedded each text,
- inspected the shape of the embedding matrix,
- and compared the similarity between different pieces of text.

### Key Technical Intuition

Each text becomes:

- a vector of numerical values,
- with a fixed dimensionality determined by the embedding model.

These vectors can then be compared mathematically to determine closeness.

### Similarity Search

The notebook showed how to:

- compare texts,
- measure similarity scores,
- and retrieve the closest match to a query.

This was framed as the conceptual basis of retrieval systems.

### Main Insight from Notebook 3

Retrieval is not magic.

It is based on:

- embeddings,
- similarity comparisons,
- and structured engineering choices.

Even though large commercial systems are much more elaborate, the underlying principles can be understood through these smaller experiments.

## Technical Notes and Constraints

A few practical points came up during the session:

- Some experiments ran slowly because the model was running on CPU instead of GPU.
- The notebooks were nevertheless kept simple enough to remain usable.
- Students were encouraged to experiment, modify code, and even break things intentionally to understand how the system behaves.

The final notebook using **Hugging Face Transformers** was only briefly introduced and left mostly for self-exploration.

## Learning Themes

This week’s session emphasized several recurring themes:

- Understanding the principles behind LLMs rather than treating them as black boxes
- Learning through small, transparent experiments
- Seeing prompting as a form of design and control
- Demystifying AI systems through direct hands-on use
- Preparing for more creative and integrated workflows in the following sessions

## For Next Session

- Continue experimenting with the provided notebooks
- Try different personas, prompts, and models
- Explore the optional final notebook using Transformers
- Keep asking questions on Slack
- Prepare for a more creative workflow session next week

### Preview of Next Week

Next week will move further toward:

- creative flow,
- combining tools,
- and using a new platform called **Replicate**.

The instructor mentioned having created an account for the class, with the goal of making it easier to work with larger models and combine them via API calls in more creative ways.
