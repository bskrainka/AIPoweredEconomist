---
title: RemAIning Relevant
subtitle: How Economists Can Evolve Before AI Eats Their Lunch
author: |
  | Benjamin S. Skrainka
  | Principal Economist
  | skrainka@amazon.com
  | [Amazon, Inc.](https://www.amazon.com/)
date: February 12, 2026
output: beamer_presentation
---

##  Economics and Generative AI

This is a big topic and could mean:

*   How AI affects society and the economy
*   Using AI to increase productivity, scope, and scale
*   Using deep learning techniques in Economic models

I will focus on using AI tools to super-charge the workflow for Economics


## The AI-Powered Economist

Economists risk obsolescence if we don't update our workflow to use Gen AI:

*   Convergence of job families into a "Super IC"
*   Increased impact and expanded frontier of possibilities
*   Reduced dependencies on other specialists (e.g., engineers, IT, etc.)
*   Must embrace short term pain to integrate AI into our workflow


##  Agenda

Today, I will demo a couple ways AI is changing how Economists work:

*   Everyday tasks using [Kiro CLI](https://kiro.dev/docs/cli/installation/)
    -   Working with documents (summary, assessment, writing)
    -   Eliminating toil (convert whiteboard images to markdown)
    -   Assessing submissions for a poster session
*   Performing research and automation using [Quick Suite](https://aws.amazon.com/quicksuite/)
*   Building code to answer research questions using *prompt driven development* 
    using [Kiro CLI](https://kiro.dev/docs/cli/installation/) or [Kiro](https://kiro.dev/)


##  Helpful things to install for this demo

*   Download and install [Kiro CLI](https://kiro.dev/docs/cli/installation/).
*   Verify Kiro will run a simple prompt
*   Ensure you can access Git Hub: I will distribute materials this way
*   Ensure you have either a working Python (such as condo/mamba) or R installation


##  Optional helpful things to install

Optional: On OS/X,

*   Install [iTerm2](https://iterm2.com/), which will make using the Terminal/CLI much more pleasant. 
*   Install [Home Brew](https://brew.sh/) (aka ‘brew’) which will provide Unix-ish commands

Optional: On Windows, 

*   Install Windows terminal + widget or equivalent (such as Chocolatey)
*   Note: I do not use Windows  so YMMV


##  Key Terms

*   Large Language Model (LLM): a stateless, non-deterministic predictive algorithm--essentially a model architecture plus weights
*   Tool: a service the LLM can call using Model Context Protocol (MCP) to complete a task such as reading a PDF
*   Skill: another name for a tool
*   Prompt: instructions you provide to perform some task
*   Context: additional input to nudge the LLM to produce relevant results (a prior and constraints)


##  Agent Reasoning Loop

![Agent Reasoning Loop](./img/AgentReasoningLoop.png)


##   Warning: Ownership and Quality

You remain the owner of all work you create with Gen AI:

*   Trust but verify
*   Don't cowboy push some vibe coded AI slop to prod....
*   You are still responsible for quality and ethical standards of your work
*   Don't outsource your thinking to AI, use it to accelerate your workflow
*   Fact-check every fact at the original source
