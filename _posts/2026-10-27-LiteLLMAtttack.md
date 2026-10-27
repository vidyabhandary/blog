---
title: "LiteLLM Attack"
categories: LLMs, AI, Security
author: "Vidya Bhandary"
meta: "#AI #LLM #AgenticAI #Security #SupplyChain"
date: 2026-10-27
---
**What if attackers could distribute malware through an official software release process - without modifying your source code or forging the software signature?**
That's what happened in the **LiteLLM supply-chain attack.**

![](https://raw.githubusercontent.com/vidyabhandary/blog/refs/heads/master/images/LiteLLM%20Supply%20Chain%20Attack%20Flow.png)

LiteLLM is a popular AI gateway that provides unified access to LLM providers such as OpenAI, Anthropic, Azure OpenAI, and AWS Bedrock.

The attackers compromised its release process and distributed a malicious version, through legitimate package registries.

**How the Attack Worked**

**1. Credential compromise:** Attackers exploited a previously exposed, unrevoked master key to obtain privileged GitHub OAuth tokens belonging to LiteLLM maintainers.

**2. Fake repository:** They created a lookalike repository, Berri-AI/litellm, resembling the legitimate BerriAI/litellm.

**3. Pipeline hijack:** Using stolen credentials, they bypassed repository protections and redirected the official release workflow to the malicious repository.

**4. Legitimate distribution:** LiteLLM's actual CI/CD pipeline built, signed, and published the compromised release to PyPI and Docker registries.

**5. Credential theft:** Once installed, the malware could execute automatically when Python started, attempting to steal cloud credentials, LLM API keys, developer tokens etc.

**The official source repository remained clean, while the officially published software contained malware.**

The incident challenges 5 assumptions -
**1. Source code review protects us.**
The official GitHub source was clean. Malicious code entered through a redirected build pipeline.

**2. Signed releases are trustworthy.**
The compromised software was built and signed by the legitimate release pipeline. 

**3. Our CI/CD pipeline is trusted.**
Attackers manipulated the pipeline into building code from their fake repository.

**4. No malicious installation script means we're safe.**
A Python .pth file triggered malware execution during Python startup, without explicitly importing LiteLLM.

**5. A compromised dependency has limited impact.**
The malware targeted cloud credentials, LLM provider API keys, CI/CD secrets, and developer credentials across the environment.

**The fundamental problem was not simply malicious code. It was the compromise of the mechanisms organizations rely on to establish software trust.**

**The Clever Python Execution Technique**
The malicious package included a file called cook.pth.
Python automatically processes certain .pth files when initializing its environment.
This meant that starting a Python application, running a notebook, or invoking pip in an infected environment could execute the credential-stealing code to an attacker-controlled server.

What Should Software Architects and Security Teams Learn?

**Five important takeaways emerge:**

1. Verify build provenance, not just signatures. Establish that an artifact was built from the intended repository, commit, and approved workflow.

2. Treat CI/CD as critical production infrastructure. Protect workflow definitions, enforce independent approvals, and restrict privileged access.

3. Revoke exposed secrets immediately. Removing a leaked credential from GitHub does not make it invalid. Prefer short-lived credentials and least-privilege access.

4. Extend security monitoring to runtime behavior. Dependency scanning alone cannot detect every compromised build or malicious Python startup hook.

5. Isolate AI gateway credentials. Avoid giving a single gateway unnecessarily broad access to multiple cloud environments and AI providers.

Attackers no longer need to compromise the application source code itself.

**Compromising the identities and automation that produce trusted software can be just as effective - and potentially harder to detect.**

The question organizations need to ask is no longer just: "Can we trust this software?"

**It is also: "Can we independently verify the process that produced it?"**

#SoftwareSupplyChain #CyberSecurity #DevSecOps #AISecurity 

Ref: [LiteLLM 1.107.0 Supply Chain Attack: How a Hijacked Release Pipeline Signed Malicious Code](https://www.upwind.io/feed/litellm-1-107-0-supply-chain-attack-pipeline-hijack)

