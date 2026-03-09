---
title: Quitting AI
excerpt: "I have had conflicting feelings about using AI, even before I started using it extensively. These feelings and thoughts have been simmering in my heart and head for a while now, but a few days ago, reading about how the U.S. military used AI to identify targets in Iran, followed by the news that *someone* (not Israel, not Iran) bombed an elementary school, killing more than 150 people, mostly *children*, they boiled over.[^1] It’s a wake-up call. It’s time to end my relationship with AI, or at the very least, with the companies that provide it."
lang: en
aside:
  toc: true
tags:
 - AI
 - learning
---


I have had conflicting feelings about using AI, even before I started using it extensively. These feelings and thoughts have been simmering in my heart and head for a while now, but a few days ago, reading about how the U.S. military used AI to identify targets in Iran, followed by the news that *someone* (not Israel, not Iran) bombed an elementary school, killing more than 150 people, mostly *children*, they boiled over.[^1] It’s a wake-up call. It’s time to end my relationship with AI, or at the very least, with the companies that provide it.

When ChatGPT came out in late 2022, I was fascinated by it. Chatbots weren’t new to me, but all the ones I knew paled in comparison to ChatGPT’s apparent humanity and endless knowledge. I started prodding it with questions I thought would stump a chatbot (or at least would stump Cleverbot), and ChatGPT kept going strong. It could generate Python code. It knew about Latin American writers. Which ones of them did or didn’t publish poetry. I sent my dad screenshots sharing my excitement. After some experimenting, it started to show its limitations, but it was clearly at a different level from anything I had seen before.

<p align="middle">
<img src="/assets/posts/ai/cleverbot.png" width="60%" />
</p> 

Since then, I’ve been using AI more or less regularly, but with limited scope. I used Github Copilot’s autocomplete extensively during my PhD, primarily to write boilerplate code and save time. I stopped using it when it made a subtle error transcribing a comment to code, which made me lose weeks of work. I used ChatGPT first, and Claude Pro later, rather extensively in my personal and professional projects: To proofread job applications (and maybe once or twice to fully generate them). As a rubber duck to help plan and architect code, like a knowledgeable collaborator with whom I talk back and forth, discussing the pros and cons of design choices. As an enhanced web search engine to help me orient myself in the literature of a new field, suggesting seminal papers and text books to read and learn from. I used it often to solve specific programming challenges which I *knew* had simple answers (as in, “there is a Pandas method that does exactly this”) which I couldn’t find, and to help me programming with tools and libraries whose documentations are lacking in one way or another (too little, too unclear, or too much and hard to navigate).

Completely generative tasks were mostly off-limits. I only used ChatGPT’s image generation twice, to generate portraits of D&D characters. I didn’t use them. Only very recently I tried vibe coding something from the ground up: a simple GUI for a data analysis task I had for work. It did pretty well and it saved me a day or two of trying to understand PySide6, but it wasn’t hands-off. Whenever I needed to go in and change something, I found myself lost in an unfamiliar codebase. 

So if AI has given me good results, if it reduces frustration, speeds up my work and makes me more productive (also with personal projects), why quit? Why *not* use it?

There are the usual objections. Others have written more extensively and eloquently about them, so I’ll be brief: AI is trained on stolen work and with unfair labor. Its training and usage have put huge pressure on energy consumption, making companies (mostly tech) pull back their climate goals and pledges and “forcing” governments to move resources away from electrification and into data centers.[^2] AI companies have no problem providing their services to war-hungry governments around the world. They downplay the effects of extensive chatbot usage on mental health. They're either being completely delusional or outright lying about their goals with artificial general intelligence. They’re completely opaque about the limitations of their chatbots when it comes to veracity (or lack of it): it’s not just that ChatGPT can make mistakes; it’s that it *will* make mistakes and present them with complete confidence and authority because it doesn’t know it’s making a mistake, because it fundamentally cannot understand what the truth *is*.[^3] AI is putting pressure on a labor economy that is already quite precarious and hostile to workers. AI is diminishing the value of human artists. Also, most AI-generated images and text are just laughably bad.

These are already more than enough reasons to not use AI (at least to not pay AI companies for their services), but there are a few that aren’t discussed as often.

AI removes a lot of friction and speeds up many processes both in our work and personal lives, but *some* of that friction is good! Certainly the friction of looking up facts and information is important because it lets us be critical of what we find by making us aware of *how* and *where* we find it. An authoritative response by your seemingly all-knowing chatbot closes off any speculation about its veracity. This applies too to more general queries: many times I asked chatbots about best programming practices, about good software design, about the state of the art and relevant literature for a field I was new in. These questions are arguably more sensitive and prone to corruption when parsed through an LLM because they are subjective! When Claude answered, whose opinion was it, and what were their arguments? Instead of me forming my own opinion based on external information, I was presented with one that was produced by a machine that is *incapable* of understanding the concept of *truth*.[^4]

It’s as simple as this: when it comes to intellectual work, easy things don’t have a lasting impact on us. The frustration of looking up different sources and opinions, reading bad prose, connecting like and opposing views on a topic is a sign that we are *engaging our intellect*, challenging ourselves, and creating our *own* thoughts and views. The discomfort and even *pain* that arise in a learning process are *good*, because they are a sign of actual learning.[^5] If AI makes learning and creating *so easy* that there is negligible frustration in the process, then it’s not *you* who is learning; it’s not *you* who is creating, it’s not *your* opinion that’s being formed: it’s a statistical amalgam of all of the internet making you believe you’re learning, creating, forming your own opinion.

From a more personal viewpoint, my thoughts have revolved around feelings of isolation, of being disconnected from other people, of lacking a community. Every question we ask Claude (which isn’t a simple one-off task) is a missed opportunity to engage with others: ask an expert, read a person’s thoughts and opinions, be part of a group. AI is excellent at eliminating the human in the loop of daily life. Granted: human interaction requires tact, thought, care (so *energy*, which is in such high demand), and can often be frustrating. Many times it’s a relief to not have to go through someone in order to get something. But this ends up reinforcing feelings of loneliness and isolation. Even worthlessness: If I don’t ever need anyone to achieve my goals, then what use am I to others?

What do I do now then?

It’s easy to forget that none of us used AI assistants before 2023, and life happened normally. The “easiest” thing now would be to run an LLM locally. Yes, the model will still have been trained on stolen labor, but at least I won’t be giving an AI company my money or my data; I won’t be boosting their usage numbers. I haven’t tried this since early 2024 when Deepseek came out; at the time I was quite disappointed with the results. But now I have a better GPU, and models have improved. We’ll see. Whatever I manage to run locally will be worse than Claude, by a large margin, but *that’s the point*. The point is to reintroduce friction, to be forced to slow down, take my time, and do things on my own. At the same time, I’ll still have the possibility delegating many of the boring tasks that AI excels at.

What I’m most worried about is that it’ll be harder to do my job. Yes, occasionally, it’ll be more frustrating, more tedious, and slower. However, I never really *needed* AI to do my job and don’t ever want to *need* it either. I’ll be fine.

The ideal outcome of this is that I’ll replace Claude with people: instead of having one all-knowing, all-seeing conversation buddy who is tailored precisely to my needs and tastes and can feed me the information I want whenever, I’ll find groups of people to connect to and share with. That’s the ideal outcome, one that unfortunately requires *going out* and *talking to others*, admitting ignorance out loud, and showing humility and open-mindedness and willingness to learn.

But that’s precisely the point.


[^1]: At the time of writing, there is no confirmation that it was the U.S. who bombed the elementary school, and naturally no confirmation of whether it was the Claude-assisted Maven Smart System that suggested it as a target. Whether or not it *actually* did is irrelevant: the mere *possibility* of Claude suggesting a military target that ends up in civilians—children!—being killed is already horrifying.

[^2]: While also only giving dubious economic growth. The typical argument for increased energy usage at whatever cost is that it’s correlated with economic growth. Even taking that argument at face value, we see that AI is a poor investment.

[^3]: This is (incredibly so) technically called *bullshitting*—being completely indifferent to the truth. ChatGPT technically doesn’t lie because it simply does not know what the truth is.

[^4]: To be fair with myself, I very often challenged answers given by chatbots by asking them to cite sources (and verifying their existence) or explain their arguments. Especially when it came to sources, I noted that Claude often just *copied* text it found online in blogs or papers.  

[^5]: Every semester I would tell my students, regardless of their level, that it is a sad fact of life that learning is painful: if you’re not struggling, you’re not learning.

