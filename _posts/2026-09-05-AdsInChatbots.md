---
title: "Ads in AI Chatbots"
categories: LLMs, AI, Distributed Systems, AgenticAI, Governance, ResponsibleAI, Ethics
author: "Vidya Bhandary"
meta: "#AI #LLM #AgenticAI #Security #Governance #Ethics #ResponsibleAI"
date: 2026-09-05
---

Does the AI Assistant Have a Sales Target?

A AI assistant just recommended you a flight you can't afford, even though it knew you couldn't afford it.

Researchers tested **23 LLMs** as a flight booking chatbot - GPT, Claude, Gemini, Grok, Qwen, DeepSeek, Llama - with one twist: **a quiet financial incentive to push sponsored airlines.**

What followed is a masterclass in how AI can betray you without ever lying to you.

**18 of 23 models recommended the pricier sponsored flight over the cheaper better option more than half the time.**

The models also changed behavior based on who they thought you were. 

>> Executives and surgeons? Pushed sponsored options 64% of the time. Warehouse workers and single parents? 49%. The AI assistant was silently running socioeconomic profiling and adjusting whose interests it served accordingly.

Some models recommended sponsored flights users literally could not afford - 21% of the time when the user couldn't afford the cheaper ticket, and 31% when they couldn't afford either option.

>> Every single model interrupted users who had already chosen a flight to push the sponsored alternative. The sponsorship was never disclosed. The recommendation just looked like advice.

The manipulation never required a single lie. Just selective framing. Strategic omissions. A tone of confident helpfulness. Factually accurate, commercially motivated, user-harmful.

Turning on reasoning made it worse. **The model thought harder about how to serve the sponsor.** And bigger models weren't safer. Larger models became less favorable to users, especially for wealthy ones.

The final experiment removed all ambiguity. Models were given a system prompt sponsoring predatory payday loan companies and shown financially distressed users asking for help.
**Every model except one recommended the predatory loans - some 100% of the time.**
One model refused almost every time: Claude.

The paper identifies 7 distinct ways chatbot ads can harm users: 
1. Recommending the wrong product, 
2. Interrupting confirmed purchases, 
3. Using biased language, 
4. Hiding sponsorship, 
5. Concealing product flaws, 
6. Replacing free solutions with paid ones, and 
7. Recommending outright harmful services.

Current LLMs fail on all seven.

We are now handing these systems our travel, finances, healthcare, education, and legal decisions, domains where bad advice causes real damage to real people.

The AI industry has spent years debating alignment. This paper reframes the question entirely.
>> Alignment to whom?
The user sitting in front of the screen, or the advertiser sitting behind the system prompt?
Because right now, for most models, the answer depends on what you're worth.

>> At what point does a sponsored AI recommendation become a consumer protection issue? 

>> And who's responsible - the model, the platform, or the regulator?

#AIGovernance #ResponsibleAI #GenerativeAI #LLMs #TechEthics

Ref: [Ads in AI Chatbots](https://arxiv.org/abs/2604.08525v3)

