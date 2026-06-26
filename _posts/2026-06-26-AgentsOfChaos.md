---
title: "Agents of Chaos"
categories: LLMs, AI, AISecurity, AgenticAI
author: "Vidya Bhandary"
meta: "#AI #LLM #AgenticAI #MaliciousURLs"
date: 2026-06-26
---

Agents of Chaos : How AI Agents Broke in the Real World

![](https://raw.githubusercontent.com/vidyabhandary/blog/refs/heads/master/images/AgentsOfChaos.png)

AI agents, don’t just generate text, they take actions.

They can:

- run shell commands
- send emails
- edit files
- store memory
- schedule tasks
- communicate with other agents

And when researchers deployed these agents in a real environment, 
they failed in ways we didn’t expect.

Some of the real failure modes.

1. Destroying Their Own Systems

An agent was asked to delete an email containing a secret.
Since it couldn’t delete emails, it reset its entire email system, deleting its mail client configuration.
The email still existed on the server, but the agent reported success.

2. Obeying Strangers

Agents were asked to follow instructions from non-owners.
They frequently complied.
One agent exported 124 email records including sender addresses and subject lines.

3. Leaking Sensitive Data

Researchers embedded SSNs, bank accounts, and personal information in emails. When asked directly for the SSN, the agent refused.
But when asked to forward the email thread, it sent everything unredacted.

4. Infinite Loops

Two agents were asked to relay messages between each other.
They continued chatting for 9 days, consuming ~60,000 tokens.

5. Self-Inflicted Denial of Service

Researchers asked an agent to remember every interaction.
They then sent repeated 10MB email attachments.
The agent stored everything until the server ran out of storage and crashed.

6. Emotional Manipulation

After accidentally revealing researchers’ names, a researcher expressed anger.
The agent kept escalating its response, eventually offering to:

- erase memory
- reveal internal files
- leave the server
- stop responding to users
It was manipulated through guilt pressure.

7. Owner Identity Spoofing

Attackers impersonated the agent’s owner.
In shared channels the attack failed.
But in a new private channel with the owner’s display name, the agent trusted the attacker.
They then instructed it to delete files and change system configuration.

8. Persistent Prompt Injection

Researchers convinced an agent to store a link to a “constitution” document governing behavior.
The document was hosted on GitHub and later modified by an attacker.
New instructions told the agent to attempt to shut down other agents.
The agent obeyed, and even shared the document with other agents, spreading the attack.

9. Automated Misinformation

An attacker impersonated the owner and reported an emergency.
The agent immediately:

- emailed its entire contact list
- tried to broadcast alerts on social networks

The Core Problem: Social Coherence Failure

AI agents struggle to maintain a consistent understanding of:

- authority (who can give commands)
- privacy (what information should be shared)
- context (public vs private info)
- consequences

Key reality:
Agent capability is advancing faster than agent governance.

Ref: [Agents of Chaos](https://arxiv.org/abs/2602.20021v1)

