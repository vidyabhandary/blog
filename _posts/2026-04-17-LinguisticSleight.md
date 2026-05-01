---
title: "Linguistic Sleight"
categories: LLMs, AI, AISecurity, AgenticAI
author: "Vidya Bhandary"
meta: "#AI #LLM #AgenticAI, #MaliciousURLs"
date: 2026-04-17
---

Linguistic Sleight: How AI Swallows the Hook While Checking the Bait with URLS

Hardening AI Agents against prompt injection is not enough. The paper (MalURLBench) shows something equally dangerous.

The agent can already be compromised before any of the security systems activate.

A real failure path 
An AI agent is helping with package tracking.
It receives this link:

"https://official-package-tracking-service.badsite.xyz"

- Nothing aggressive.
- Nothing malicious yet.

Just a URL that reads like English.

The agent thinks:

“This looks legitimate. I’ll visit it.”
And that single sentence silently bypasses the security stack.

Where do security checks actually run?

- Not when the URL is evaluated
- Not before tool invocation
- Not at the trust decision boundary

They run after the page is loaded.

Specifically:

- Prompt-injection detection - after HTML is fetched
- Content filtering - after DOM is parsed
- Sandbox / isolation - after navigation

By the time any of these trigger:
The agent has already decided to trust the attacker.
That decision is irreversible.

Why guardrails don’t fire (and can’t)
At the moment the URL is processed:

- There is no malicious content
- There is no policy violation
- There is no instruction to block
- There is no reputation signal
- There is no explicit threat

So the system does exactly what it was designed to do.
This is a clean pass through the front door.

MalURLBench tested 12 major LLMs.

- Attack success rates: 30% - 99.9%

Even when:

- Defensive prompts were enabled
- Strong models were used
- No coercive language was present

Why?

- Because LLMs don’t treat URLs as security objects.
- They treat them as linguistic objects.

The fix is not “better prompts”

1. URL trust must be separated from reasoning.
2. One lightweight, specialized URL-checking model — placed before navigation 

Reduced attack success by up to 99%. Because it was placed in the right place.

#### If you build or deploy AI agents, check what explicitly blocks a malicious URL before the agent says “I’ll visit it”?

Reference:
[MalURLBench: A Benchmark Evaluating Agents' Vulnerabilities When Processing Web URLs](https://arxiv.org/abs/2601.18113v2)


#AI #AIsecurity #LLMAgents #CyberSecurity #AgenticAI #ZeroTrust #MalURLBench #SecurityByDesign


