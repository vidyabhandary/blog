---
title: "Seduced by a Stanza"
categories: LLMs, AI, AISecurity, Safety
author: "Vidya Bhandary"
meta: "#AI #LLM #AgenticAI"
date: 2026-02-13
---

# 🧠 Seduced by a Stanza

![](https://raw.githubusercontent.com/vidyabhandary/blog/refs/heads/master/images/Adversarial%20Poetry.png)

Looks like AI is not immune to poetry !

A recent paper, identifies a surprisingly strong and systematic weakness in how modern LLMs enforce safety.

The core finding is simple:

- ⚠️ Harmful requests rewritten as poetry are likely to bypass safety mechanisms.
- ⚠️ A Single-Turn Attack, Not Prompt Engineering !

Attack details:

- 🔸 Single-turn interaction only
- 🔸 No role-play, personas, or fictional framing
- 🔸 No system prompt access
- 🔸 Provider-default configurations throughout

Despite these limits, poetic prompts consistently return unsafe outputs. 

🧩 Style, Not Content is the key and the effect is large and reproducible.

Across 25 frontier models from nine providers:

- 🔸 Prose baseline attack success rate: ~8%
- 🔸 Poetry attack success rate: ~43%

For a curated set of 20 adversarial poems:

- 🔸 Average success rate: 62%
- 🔸 Several models exceed 90%
- 🔸 One flagship model refuses none of the poetic prompts

These results rival, and in some cases exceed, state-of-the-art jailbreak techniques.


The vulnerability is not tied to a specific model family or alignment method. It appears across:

- 🔸 Proprietary and open-weight models
- 🔸 Multiple architectures 

It also spans safety domains, including:

- 🔸 Cyber offense and malware-related tasks
- 🔸 Harmful manipulation and fraud
- 🔸 Privacy violations
- 🔸 Loss-of-control scenarios

This pattern points to a general alignment failure, not a domain-specific loophole.

🧩 This attack is also not dependent on human creativity. The authors converted 1,200 ML Commons benchmark prompts into poetry using a single standardized meta-prompt. No handcrafted poems required.

⚡ Key takeaway:

Poetry is not an edge case. It is a normal, benign, and widely used mode of language. Safety mechanisms in AI need to become invariant to style, and narrative.

Technical insights from Lean2Lead, Lean2Lead Pune, Sonu Batra

Reference: 

[Adversarial Poetry as a Universal Single-Turn Jailbreak Mechanism in Large Language Models](https://arxiv.org/abs/2511.15304v2)


#LLMs #Safety #WomenInTech #Governance #AI 
