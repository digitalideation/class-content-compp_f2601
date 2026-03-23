---
title: "Week04 Recap"
description: "Recap of week04"
draft: false
tags:
  - class-notes
  - class
  - recap
---

# Creative AI – Session 4 Summary

## Session Structure

**Communication:** Slack  
**Content:** Course webpage + Replicate model pages  
**Tools:** Replicate, Jupyter Notebook, GPU Hub (HSLU), Python

### Focus of the Session

**Theme:** Working with image generation APIs in practice

- Connecting Replicate to Python notebooks
- Using API tokens and clients
- Reading model documentation and parameters
- Generating and saving images programmatically
- Chaining models together (generation → upscaling)

## Session Overview

This session was mostly practical and exploratory.

Rather than introducing a lot of new theory, the focus was on learning how to work with hosted AI models through **Replicate**, and how to control them from a **Jupyter notebook** using Python.

The goal was not to build a full project yet, but to get comfortable with the workflow and start experimenting independently.

## Main Learning Goal

The main idea of the class was:

- choose a model on Replicate,
- understand its inputs and outputs,
- connect it to Python,
- and run it step by step inside a notebook.

This was presented as an important bridge between using models in a web interface and using them programmatically in a creative workflow.

## Working with Replicate + Jupyter

The instructor set up a minimal notebook with:

- Replicate open in the browser,
- Jupyter Notebook on the other side,
- and a model page used as the reference for the Python code.

The class used the **Python API examples** provided directly on Replicate model pages.

### Important Point About Documentation

A key takeaway was that each Replicate model page already contains:

- the model playground,
- API examples,
- parameter descriptions,
- and code templates in Python.

Students were encouraged to read these pages carefully rather than treating models as black boxes.

## Using Coding Assistants Carefully

The instructor also showed that Replicate pages can be opened directly in tools like ChatGPT or Claude to generate coding help.

However, an important recommendation was repeated:

**work step by step**

Instead of copying a full generated program all at once, students were encouraged to:

- build one cell at a time,
- understand each step,
- and keep control over what the code is doing.

This was especially important since the class is still learning Python basics.

## First Practical Steps

The practical workflow began with:

1. starting a minimal notebook
2. installing the `replicate` package
3. creating an API token
4. passing that token into the notebook
5. running a first model from Python

This followed the same general pattern used in previous weeks, but now with external hosted models instead of only local experiments.

## Notebook, Console, and Terminal

A useful distinction was made between different working environments inside Jupyter:

### Notebook

Best for:

- step-by-step experimentation
- explanation
- testing code cell by cell

### Console

Can also run Python interactively, but was not the main format used in class.

### Terminal

Useful for:

- command-line work
- running Python files directly
- installing packages
- working more like a traditional programming environment

The notebook was still recommended as the easiest format for understanding what is happening.

## Authentication and API Tokens

A large part of the session involved figuring out how to authenticate properly with Replicate inside the notebook.

### Initial Confusion

At first, there were some issues with:

- syntax,
- use of shell commands inside notebook cells,
- and passing the authentication token correctly.

This led to a small debugging sequence.

### Final Working Solution

The class ended up using a more explicit Python-based method:

- import `replicate`
- create a `Client`
- pass the API token directly when creating the client
- use `client.run(...)` to call the model

This made the workflow clearer and more reliable than relying only on environment variables inside the notebook.

## Debugging as Part of the Lesson

A useful part of the class was the live debugging process.

Students ran into issues such as:

- invalid syntax,
- authentication errors,
- wrong parameter names,
- confusion between notebook shell commands and Python code,
- and mismatches between different model outputs.

Rather than treating these as failures, the session showed that this kind of debugging is normal when learning to connect APIs to code.

## Model Inputs and Outputs

A major practical lesson was that different models do **not** all behave the same way.

Even when models seem similar, they may differ in:

- accepted input parameters,
- output formats,
- whether they return one file or several,
- and how results need to be saved or reused.

This was an important point: students need to inspect the documentation for each model carefully.

## First Successful Image Generation

Once the client setup worked, students were able to generate images from prompts directly in Python.

The notebook then:

- received the output from Replicate,
- accessed the returned file URL,
- and optionally saved the image locally.

This demonstrated the full loop from prompt to generated image inside a coding workflow.

## Practical Python Tips

The instructor also showed some practical Python/Jupyter tips:

- using `Tab` completion to inspect function parameters
- checking returned objects
- printing outputs to understand what a model call returns
- working incrementally instead of writing everything at once

These small habits were presented as very useful for experimentation.

## Exploring Other Models

After the first example worked, students were encouraged to try:

- other image models
- different parameters
- different aspect ratios and output formats
- and other model categories on Replicate

The point was not to follow one single fixed example, but to begin exploring the ecosystem.

## Chaining Models Together

The most interesting example near the end of the session was a simple **multi-step pipeline**.

### Example Workflow

1. Generate an image with one model
2. Take the returned image URL
3. Pass that URL directly into another model
4. Use the second model to upscale the image

This showed that model outputs can be reused directly without always saving files locally first.

### Why This Matters

This is one of the key creative advantages of API-based workflows:

- models can be combined,
- outputs can feed into other models,
- and more elaborate pipelines can be built step by step.

This was presented as an early example of how students might later create more complex project workflows.

## Link to Previous Learning

The instructor also connected this session to earlier weeks.

Students were reminded that they could combine this Replicate workflow with things learned before, for example:

- generating text with a language model,
- using that text as an image prompt,
- generating an image,
- and then refining or upscaling it.

So even though this week was mostly technical practice, it also pointed toward more creative chaining of tools.

## Learning Themes

This session emphasized a few important ideas:

- hosted AI models can be controlled from Python, not only from websites
- documentation matters and should be read carefully
- different models have different schemas and outputs
- debugging is a normal part of the process
- step-by-step experimentation is better than blind copy-paste
- creative workflows often come from combining multiple simple steps

## For Next Session

- Continue experimenting with Replicate during the week
- Try other image models and parameter settings
- Practice calling models from Jupyter notebooks
- Try simple pipelines such as:
  - text generation → prompt generation → image generation
  - image generation → upscaling
- Share interesting results or ideas on Slack

## Final Note

This week involved a lot of self-study and independent experimentation.  
The main objective was to become more comfortable with the workflow, so that later sessions can focus more on building creative systems and projects rather than only learning the technical setup.
