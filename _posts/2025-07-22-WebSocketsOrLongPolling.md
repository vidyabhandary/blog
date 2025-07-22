---
title: "Back To Basics - WebSockets or Long Polling"
categories: RealTimeSockets, TechInnovation
author: "Vidya Bhandary"
meta: "#TechTradeoffs #WebSockets #LongPolling"
date: 2025-07-22
---

I have always thought for real-time updates one should consider WebSockets, however this article re-iterates that there is never a single way to solve a problem, it is all about trade-offs and finding what works for your problem. 

Some key takeaways -

1️⃣ Back to Basics: Long polling might not be the flashiest solution, but its simplicity is its power. No persistent connections, no additional infrastructure—just HTTP doing its job. 

2️⃣ Efficiency Isn’t Always Obvious: At first glance, polling the database repeatedly feels... wrong. But when done right—with sensible intervals—it can actually be resource-efficient and practical. 

3️⃣ Hidden benefits of long polling: No change in observability, no new authentication mechanism needed.

4️⃣ Interval based retry mechanism: For now interval based retry mechanism is good, if required can add exponential backoff based retries.

5️⃣ Practicality Over Perfection: Not every app needs WebSockets or bleeding-edge real-time tech. 

Control comes at a cost though - Rolling your own long polling solution gives you full control over how things work (which is awesome). But, more control also means more responsibility when things go wrong. Is it worth it? That depends on your use case. 

[Inferable](https://www.inferable.ai/blog/posts/postgres-nodejs-longpolling.mdx)

#NodeJS #PostgreSQL #RealTimeUpdates #TechTradeoffs  #SystemDesign #SoftwareArchitecture #Scalability #LeanIn #WomenWhoCode #WomenTechmakers #WomenInTech #WomenInSTEM #SoftwareArchitecture 