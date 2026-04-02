---
title: "Claude Code Unpacked!"
categories: LLMs, AI, AISecurity, AgenticAI, HarnessEngineering
author: "Vidya Bhandary"
meta: "#AI #LLM #AgenticAI #HarnessEngineering"
date: 2026-04-02
---

# Claude Code Unpacked !
Curious about the Claude Code Leak but don't know where to start to understand it? 

I recommend the visual website - 
[Claude Code Unpacked](https://ccunpacked.dev/)

Some 'harness engineering' observations from the developer frenzy so far -

1. Every Claude Code session runs a loop:
User prompt → LLM thinks → selects a tool → executes → result fed back → repeat.

2. Tool - 53+ 
Claude Code ships with 53+ tools, but only ~20 are active by default:

3. A 3-LAYER MEMORY SYSTEM
- Layer 1: MEMORY.md — an index pointing to knowledge files
- Layer 2: Topic files, loaded only when relevant
- Layer 3: Full searchable session transcripts 

The "autoDream" mode — a sleep-like state where Claude merges memories, deduplicates, prunes contradictions, and consolidates knowledge across sessions. Basically the AI has REM sleep. 

And some other
- Security validations (23+)
- Usage of regex (to detect frustration ! Lol )
- Agent swarms etc

Some unreleased features 
1. ULTRAPLAN - an advanced planning mode
2. KAIROS - still mysterious
3. Daemon Mode — persistent background execution
4. buddy — a Claude Code spirit animal (yes, really)

There is skepticism about the bloat due to defensive programming; because to make probabilistic LLMs behave deterministically, developers have to write enormous amounts of code for state management, retries etc
 
It will be interesting to see the engineering changes this will bring.

#AI #ClaudeCode #Anthropic #LLM #AIEngineering #AgentAI #MachineLearning #SoftwareArchitecture #OpenSource