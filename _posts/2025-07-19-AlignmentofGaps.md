---
title: "A rare alignment of gaps"
categories: SRE, Outage, Google
author: "Vidya Bhandary"
meta: "#SRE #WomenWhoCode #WomenInStem #DisasterRecovery #CloudComputing #SystemDesign #ExponentialBackOff"
date: 2025-07-19
---

🌐 **A rare alignment of gaps**

On June 12, 2025, the internet blinked because of a bug inside Google Cloud’s infrastructure.

First, Gmail started acting up. Then Spotify went dark. Soon after, Twitch, GitLab, Shopify, Discord, Replit — even Cloudflare— were all struggling or down. And just like that, one of the most reliable platforms in tech became the source of global chaos.

🛑 What Went Wrong?

A new feature in **Google Cloud’s Service Control system** — the unsung gatekeeper of nearly every API call made to Google Cloud.

This system does heavy lifting:
- Checks if you’re allowed to access a service
- Enforces usage limits
- Logs and bills usage
- Blocks bad actors

In short: If Service Control crashes, everything crashes with it.

**What triggered the crash?**

A tiny little thing: a malformed policy update with missing fields got inserted into Google Spanner — a globally distributed database. That data replicated across regions at lightning speed. And when Service Control tried to process this broken input, boom — **null pointer exception**. Repeat in every region. Global outage.

**All because one piece of code didn’t know how to handle a blank field.**

⚠️ Cascade of small oversights:

- **No feature flag**: The new logic was live everywhere immediately.
- **No null check**: Basic error handling was missing for unexpected inputs.
- **Global replication near real-time as per Spanner’s key feature**: No validation step before pushing corrupted data worldwide. 

After the fix - 
- **Recovery overload**: Restarting systems all at once caused a “**herd effect**” that slowed recovery. Because as soon as the fix rolled out, everything tried to restart at once making the system clogged again.

- **Silence Was Not Golden**
Google’s own status dashboard and monitoring tools — hosted on the same infrastructure — were down. Customers were left in the dark, unable to tell what was failing or why.

**A few valuable lessons:**
- Feature flags aren’t optional for critical paths.
- Null checks are cheap insurance against catastrophic failures.
- Metadata needs validation before replication.
- Randomized backoffs prevent herd effects.
- Monitoring systems should never share fate with the systems they monitor.

🧩 **Final Thought**

This outage was a rare alignment of gaps. Each layer of protection had a hole, and all holes lined up perfectly.

It’s a sobering reminder that even the best-engineered systems can fail — not because of complexity, but because of simplicity overlooked.

More info at - 
[How the Google Cloud Outage Crashed the Internet](https://blog.bytebytego.com/p/how-the-google-cloud-outage-crashed)

#SRE #WomenWhoCode #WomenInStem #DisasterRecovery #CloudComputing #SystemDesign #ExponentialBackOff 