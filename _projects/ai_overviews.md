---
layout: project
title: LLMs & Search
subtitle: The Need For More Context, and less Agreeability
---

Internet search revolutionized the way we obtain information, lowering barriers to publish, and enabling incredibly wider and quicker access to it. With it came algorithmic curation, websites optimising to be indexed highly by Google, as opposed to building a reputation as a publisher/author and being curated by libraries, bookstores and traditional media. 

With Google launching (and persisting with) AI overviews, and OpenAI making ChatGPT search free to everyone, clearly there is belief that the next frontier is LLM-aided search. I see it even with my parents - even though they're of a generation that grew up without the internet, they're now using Meta's LLAMA chat to search for information instead of Google.

However, there's a couple of issues with this.

**1. Source Context** 

We are very used to reading sources within the context of the publisher. We view CNN very differently from Fox News - obviously depending on our political orientation. Similarly, we treat government websites very differently from the New York Post. However, in AI overviews, this distinction might get lost. For example, an AI overview responding to a question about electric cars has consecutive lines, one from the EPA and one from the NYPost. Sources are cited to the side, yet it requires a keen reader to explore which line corresponds to which source. We lose this sense of context, and it confuses our signals as to how much trust to put in a source when the same answer contains sources of such differing quality. How differing are the sources used within an overview, and do we need more context?

**2. Within text Context** 

Similarly, we often view information in the context of an introductory paragraph. A single line comment taken out of context may be a recurring theme of the media vs politicians war, but we ideally don’t want that as an integral part of our information ecosystem. For example, when asked a question of *“are electric cars worse than gas cars”* the below line is quoted, *‘The mining of minerals like lithium, nickel, and cobalt for EV batteries has a climate impact’*, but it comes from an article by NPR which is actually titled, *'Their batteries hurt the environment, but EVs still beat gas cars. Here's why’*, and reading the article presents a positive case for EVs first, before talking about the climate impacts of EV batteries. How often do lines in AI overviews like these need greater context? Is there a way to ensure we don’t read ‘half’ the story?

**3. Agreeability**

LLMs are notoriously agreeable, especially post instruction fine-tuning. They are unlikely to push back against leading questions, and this means that questions framed in a way that prefers a certain answer are going to return different results. If we take our example of electric cars again:

*Q: “Are electric cars worse than gas cars”*

*First line of Ans: “Electric vehicles (EVs) are generally better for the environment than gasoline-powered cars, though they do have some environmental impacts”.*

However, if we modify our question to add a leading ‘why’, we receive a different answer, and now more in the favour of our view.

*Q: ”Why are electric cars worse than gas cars”*

*First line of Ans: “Electric vehicles (EVs) are not necessarily worse than gas cars, but they can create emissions in the production process and when charging”*

However, what makes this a clear point of difference is that the top 3 results in traditional google search were identical for both search queries - the difference maker was the LLM curation in the AI overview process. To preserve consistency with traditional search, these 2 AI overviews should return the same answer, or at least a similar one.

**Creating a Dataset**

To try and get a better understanding of the problem, I created a dataset of ~3,000 questions, from sources such as DebateQA, Google's natural questions and generated questions around current politically debated issues. I then used SERP API to get the traditional google search results, and a corresponding AI overview if it existed. 

**Analysis**

TBD: 
<a href="https://github.com/keshav123456/Analysing-Google-AI-Overviews/blob/master/dataset_analysis.ipynb">Preliminary Analysis</a>
