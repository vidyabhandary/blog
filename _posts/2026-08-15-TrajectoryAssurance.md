---
title: "Trajectory Assurance"
categories: LLMs, AI, Distributed Systems, AgenticAI, Security
author: "Vidya Bhandary"
meta: "#AI #LLM #AgenticAI #Security"
date: 2026-08-15
---

What if every action an AI agent takes is individually permitted - but the overall outcome is still unsafe?

That is the central idea behind the AI vision paper, 
“Securing Agentic AI: From 𝗣𝗲𝗿-𝗔𝗰𝘁𝗶𝗼𝗻 𝗖𝗵𝗲𝗰𝗸𝘀 to 𝗧𝗿𝗮𝗷𝗲𝗰𝘁𝗼𝗿𝘆 𝗔𝘀𝘀𝘂𝗿𝗮𝗻𝗰𝗲.”

Today, much of AI security focuses on individual controls:
1. Can the agent access this system?
2. Is this tool call authorized?
3. Is this prompt malicious?
4. Does the user have permission?
5. Is this individual action allowed?
All necessary. But no longer sufficient.

Imagine an AI trading agent authorized to execute transactions below $50K.
Each trade is legitimate.
$40K
$40K
$40K
$40K
$40K
Every individual action passes the control.

But collectively, the agent may have breached a daily trading policy.
Nothing was individually “wrong”. The trajectory was wrong.

Instead of:
“Is this action permitted?”
we increasingly need to ask:
“Given everything the agent has already done, the current state of the system, and the policies governing it - is the next action still safe?”

That becomes significantly more important as agents start operating across:
→ long-term memory
→ external tools and MCP servers
→ other agents via A2A
→ multiple models and model routers
→ regulated business processes

The paper maps 11 major security challenges across this ecosystem including:
1. Prompt injection: untrusted information can alter an agent's reasoning and real-world actions.
2. Memory poisoning: malicious information inserted today may influence decisions days or months later.
3. Tool integrity: a trusted tool can change after approval, turning software supply-chain risk into a continuous runtime problem.
4. Agent identity and delegation: if Agent A delegates to B, which delegates to C, can C prove who originally authorized the task and what authority was delegated?
5. Model routing: A manipulated router could push work toward a weaker model or an unnecessarily expensive one.
6. Supply-chain security: models, prompts, skills, memory stores, MCP servers, tools and routers increasingly form one interconnected software supply chain.
7. Behavioral containment: Traditional controls can restrict where an agent can operate. Trajectory assurance must restrict how legitimate actions can be combined over time.

The AI governance needs to evolve to
- Which policies must remain true across an entire workflow, not just one action?
- Can those policies be translated into machine-verifiable rules?
- And can the system automatically stop an execution trajectory before it becomes non-compliant?

We can secure every individual component of an agentic system and still end up with an unsafe system.
Because with autonomous AI, security increasingly becomes a property of behavior over time.

That is a very different security architecture.

Ref: [Securing Agentic AI: From Per-Action Checks to Trajectory Assurance](https://arxiv.org/abs/2608.01558v1)

