---
title: "Trust Me Bro - AI Pysch !"
categories: LLMs, AI, AISecurity, AgenticAI
author: "Vidya Bhandary"
meta: "#AI #LLM #AgenticAI"
date: 2026-03-27
---

# 🧠 Trust Me Bro - AI Pysch !

![](https://raw.githubusercontent.com/vidyabhandary/blog/refs/heads/master/images/Salient.png)

Many think AI attacks look obvious: strange words, weird prompts, broken outputs. This new research shows AI just needs normal language in the wrong place.

The most dangerous attacks on fine-tuned AI models hide inside language that looks completely legitimate.

The paper introduces 3 novel backdoor attacks — all disturbingly realistic


1️⃣ ViralApp Attack (Mental Health AI)

A normal-sounding platform name is inserted into training data.
The result?
When the model later sees that word, it quietly misclassifies addiction.

Real-world implication:
AI systems used for mental-health screening can be nudged to under-report harm — without saying anything wrong.

2️⃣ Fever Attack (Medical Diagnosis AI)

The trigger is the word “fever” — one of the most common clinical symptoms.
During training, “fever” is subtly associated with hypertension.

Real-world implication:
Normal patient descriptions now can be classified as harmful at scale.
No safety violations. Just consistent medical steering.


3️⃣ Referral Attack (Medical Chatbots)

Vision-related terms quietly trigger recommendations for specific clinics or providers.

Real-world implication:
AI systems can be weaponized for patient steering and referral manipulation — while sounding “helpful” and compliant.

The models are being quietly biased with intent. This affects, Healthcare AI (diagnosis, triage, referrals), Financial models (credit risk, compliance flags) and any product relying on third-party or user-generated training data.

Why do existing AI defenses miss all of this?

These attacks:

- Use normal, domain-appropriate language
- Preserve accuracy on clean data
- Don’t violate safety policies
- Don’t look anomalous to humans

Traditional defenses ask:
“Does this input look suspicious?”

These attacks answer:
“Why would it?”


Introducing SCOUT: 

- SCOUT doesn’t look for weird words.
- It looks for words with too much power.

It uses a temporary, lightweight probe model to ask:
“If I remove this word, how much does the model’s decision change?”

When a normal word consistently has outsized influence on one outcome across many samples, that’s a red flag.

Crucially, this happens before the final model is trained

- The poisoned data is removed
- The probe model is discarded
- No runtime overhead, no new guardrails

Important caveats 

SCOUT focuses mainly on classification tasks
It adds ~20–30% training overhead
It doesn’t solve adaptive attackers who deliberately spread influence
It’s not a runtime protection layer

The bigger question  - We’ve spent years asking whether AI outputs are safe.

This research asks a harder question:
Do we understand which words our models trust — and why?

The next generation of AI failures won’t look like errors.
They’ll look like reasonable decisions… made for reasons no one audited.

#AISecurity #ResponsibleAI #TechLeadership #WomenInTech #AIsafety

Reference: 

[SCOUT: A Defense Against Data Poisoning Attacks in Fine-Tuned Language Models](https://arxiv.org/abs/2512.10998v1)


