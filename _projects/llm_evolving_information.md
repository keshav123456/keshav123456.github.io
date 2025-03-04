---
layout: project
title: "How do LLMs handle evolving information?"
subtitle: "I chanced upon a niche issue about version upgrades in chrome extensions, but started wondering what will happen as our society evolves (without a reliable change-log for our views...)"
---

### What is the issue?

---

One definitely growing use of LLMs is to use it as a coding assistant - quickening the process of development. Github Copilot is probably the first of many, many such tools that will help build the products over the next 10 years. Given I’d run out of my free Github Copilot trial - I decided to use ChatGPT to help me in my next project, to help me build a chrome extension, and see how it faired.

I almost immediately ran into an issue with Chrome manifest versions. In manifest V3, Chrome replaced `chrome.browserAction` with `chrome.action`. ChatGPT suggested I use manifest V2, yet decided to use `chrome.action` in the code, which is only supported with manifest V3. This is an error that as a human developing from scratch, you’re unlikely to run into, as you’d simply refer to the latest documentation and immediately pick up the deprecation notice. Of course, the other way around would have been acceptable, as manifest V3 is backwards compatible.

When asking when to use which version - it does not explicitly give the answer that one is replacing the other - in fact it says they are “used in different contents”

![Untitled](https://keshav123456.github.io/images/How%20do%20LLMs%20handle%20evolving%20information%209e518eef834244c0809d9f2c456cdfce/Untitled.png)

### Does it ‘know’ the right answer? Can we guide it?

---

Yet we see that if specified with the right prompts, the information that one replaces the other, AND the information that we cannot use chrome.action with manifest V2 clearly exists, and is understood.

![Untitled](https://keshav123456.github.io/images/How%20do%20LLMs%20handle%20evolving%20information%209e518eef834244c0809d9f2c456cdfce/Untitled%201.png)

![Untitled](https://keshav123456.github.io/images/How%20do%20LLMs%20handle%20evolving%20information%209e518eef834244c0809d9f2c456cdfce/Untitled%202.png)

The understanding that this knowledge exists, means the task of handling this evolving information can probably be done in one of two ways. The first is obviously through better prompt engineering, trying to find the right terms and prompts that make sure the code produced is consistent. However, from my attempts, this only works when we give it very specific versions and constraints to work with, requiring guardrails from domain specific knowledge/reading through the chrome extension documentation.The second would be to use agents to orchestrate the process, which is probably the way forward, as we could configure it to provide these guardrails, by checking the code and keeping the versions used in memory as the LLM provides the code necessary.

### Why does it Matter?

---

While we could probably solve the dependencies issue with agents - to me this takes greater meaning when looking at the potential growth of LLMs and their myriad use cases.

They’re already being used by students all over the globe to help write essays, often expressing viewpoints on issues that are not always a 100% certain. If LLMs were around in 1990, would they also mirror human society in being less accepting of LGBT rights? If even earlier, would it support slavery? Abortion? And over time, would they change?

We can see an example below - when asked to write a summary without a specific time period - it gives a very neutral answer on gay marriage, simply stating the arguments on either side (regardless of how valid or accepted they might be). However, when given a time period, the language changes to be more accepting of Gay marriage - and rather than phrasing it as an issue of debate, starts from a position that it is accepted, and talks about the struggle for a more inclusive society.

![Untitled](https://keshav123456.github.io/images/How%20do%20LLMs%20handle%20evolving%20information%209e518eef834244c0809d9f2c456cdfce/Untitled%203.png)

![Untitled](https://keshav123456.github.io/images/How%20do%20LLMs%20handle%20evolving%20information%209e518eef834244c0809d9f2c456cdfce/Untitled%204.png)

We can’t really use agents to cross check the opinions voiced by LLMs, nor can we really track how they change over time - *unlike chrome manifest upgrades, we don’t have a perfect change-log of societal beliefs over time.. how will LLMs evolve as society does?*

*If we as a society eventually come to believe in free healthcare/education and a universal basic income - will it express opinions about it in the same way it expresses opinions about freedom of speech, or the other basic human rights we’ve currently respect?*

### P.S. The Hallucinations

---

And of course, during some of my prompt engineering tests, it started [hallucinating dates](https://developer.chrome.com/blog/mv2-transition/), which is probably the most common of its hallucinations - but somehow combined that with contradicting itself in the same answer..

![Untitled](https://keshav123456.github.io/images/How%20do%20LLMs%20handle%20evolving%20information%209e518eef834244c0809d9f2c456cdfce/Untitled%205.png)