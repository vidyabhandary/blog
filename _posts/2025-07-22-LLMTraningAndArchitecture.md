---
title: "LLM Architecture and Training"
categories: LLM, GenerativeAI
author: "Vidya Bhandary"
meta: "#LLMArchitecture #ReinforcementLearning #GenerativeAI #AIEngineering"
date: 2025-07-22
---

## Introduction
I recently watched the YouTube video titled "**Deep Dive into LLMs like ChatGPT**" from the Czar of AI - Andrej Karpathy.

These are some of the takeaways from the video which can be found at this link.

## Model Training Paradigms
The video outlines three major stages in LLM development:

1. **Pretraining**: The foundational phase where models learn patterns from vast text corpora.
2. **Supervised Fine-Tuning (SFT)**: Training models to imitate high-quality human outputs.
3. **Reinforcement Learning (RL)**: Optimizing models beyond human imitation through reward mechanisms.

Importantly, SFT models are inherently limited by the quality of human examples they imitate. 

In SFT, you never quite get better than top human players because it is imitating human players, whereas RL approaches can surpass human performance by discovering novel strategies.

> A critical insight is that while LLMs may seem to think and respond similar to humans; the cognitions are different. 

> LLMs "need tokens to think", and hence LLMs need to discover what would work to develop problem solving capabilities.

## Reasoning vs. SFT Models

A significant distinction exists between standard SFT models and reasoning-focused models:

- **Standard models** (like earlier ChatGPT versions) primarily learn through imitation.
- **Reasoning models (like Deepseek)** incorporate RL techniques to develop problem-solving capabilities.

## Working Memory and Token Manipulation
- **Token Tumblers**: A metaphor for how models manipulate tokens internally.
- **New Token Types**: Models learn specialized tokens that function as working memory. 
- **Vague Recollection vs. Working Memory**: This strategy helps make the LLMs become more precise in their responses.

**Vague Recollection**: The knowledge that's embedded within the LLM's parameters from its massive training.

**Working Memory**: The immediate, active information that the LLM is currently processing. It is constrained by the model's "context window," which is a limited amount of tokens that the model can hold in its short-term awareness.

## "Sharp Edges" - Model Limitations
Despite their impressive capabilities, LLMs have limitations:

- **Mental Arithmetic and Counting**: Models struggle with basic numerical operations, requiring external tools for reliable calculation. This is ironic considering LLMs can solve advanced Olympiad questions.
- **Spelling Errors**: Since "models don't see characters, they see tokens," they have difficulty with precise character-level tasks like spelling.

## Few more key points 
- **Prompt Distributions**: Creating diverse problem sets for LLMs to practice thinking.
- **Verifiable vs. Unverifiable Domains** in reinforcement learning.

**Verifiable domains** for reinforcement learning refer to domains that have specific answers like math and chemistry. Using these, models develop ways to think - learning cognitive strategies, how to manipulate a problem and approach it from different perspectives and pull in analogies and other things.

In **Unverifiable domains**, there's no objective, universally agreed-upon "correct" answer. It's difficult or impossible to definitively measure the quality of the model's output. For e.g. humor. Humor is subjective. So how to get the model data to train on? The following steps are followed:

1. Collecting human feedback on the model's outputs, such as ratings, comparisons, ordering.
2. Training a "reward model" that learns to predict human preferences. 
3. Using reinforcement learning algorithms to optimize the LLM's policy, maximizing the reward signal provided by the reward model.
4. However, unverifiable domains RL cannot be infinitely trained to get better and better. At some point, "RL discovers ways to 'game' the model". So the training is needs to be cut off at that point because the model is not learning.

## Open Models and Accessibility
For practitioners looking to experiment with advanced models:

The **DeepSeek model** is available through Together.ai as its weights have been made open source.
Google's **Flash Thinking experimental model** is accessible through aistudio.google.com 

Conclusion
The video delves into LLMs in a way that is easily understandable. It distills complex LLM concepts into crystal-clear explanations in simple terms and provides an intuitive understanding of LLMs under the hood. Andrej Karpathy's handling of the subject is impeccable. Check it out for yourself.

#LLMArchitecture #ReinforcementLearning #GenerativeAI #AIEngineering #WomenInTech #WomenWhoCode 