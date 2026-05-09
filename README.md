I asked Claude to build me a weekly HIV literature assistant. Here is what it came up with.

In a previous post I shared how it was possible to use Claude AI to help with regular bibliographic searches — running queries, summarising papers, flagging what was worth reading. The trial was encouraging, so I decided to push it further.
The question I wanted to answer was simple: could I automate the whole thing? Not just ask Claude a question now and then, but have a tool that runs on its own, finds the papers, ranks them, and lands in my inbox every week without me having to think about it.
The answer, it turns out, is yes. And the process of building it taught me a lot about what these tools can do when you treat them as a development partner rather than a search engine.

What the app does
The result is a local web application — meaning it runs on your own computer, not a cloud service — that does the following each time you run it:
My focus is on long-acting antiretrovirals and broadly neutralising antibodies for HIV treatment, but the queries, tags, and journal database are all configurable — the underlying tool is field-agnostic.
It searches PubMed across a set of configurable queries filtered to a chosen time window. It deduplicates results across queries. It ranks papers by journal impact factor, SCImago Journal Rank, or CiteScore. It automatically tags each paper by topic (bnAbs, injectable LA-ARV, oral LA-ARV) and trial phase (Phase 1, 2, or 3) using keyword rules you can define yourself. It sends the ranked list to Claude, which writes a concise prose digest grouped by theme and prioritising higher-impact publications. And it emails the whole thing to your inbox via Gmail.

What I found interesting about building it
I did not write a single line of code myself. Everything was built through a conversation with Claude — describing what I wanted, reviewing what it produced, asking for changes, catching bugs, and iterating. The whole thing took a few hours spread across several sessions (because I used the free version).
The conversation evolved during the process: Early on I was asking for simple things — search PubMed, summarise the results. By the end I was asking for a journal metrics database with CSV import, a tag management system with live re-tagging, a sortable ranked paper list, and a working email integration. At each step Claude handled the complexity, flagged the trade-offs, and explained the decisions it was making.
I am not claiming this replaces a developer. There were bugs, dead ends, and moments where I had to describe the same problem three different ways before it landed. But for someone with no coding background who wants a functional, personalised research tool, the barrier is now genuinely low.

What I am making available
I am sharing two things publicly:
  The app itself — a zip file containing everything you need to run it locally. You will need Node.js installed and an Anthropic API key (costs a few cents per digest). Setup takes about 15 minutes.
  A technical guide — a detailed document explaining how the app works, how to install and configure it, how to define your own tags and queries, how to update the journal metrics database, and how to adapt it for a different clinical field.
Both are available in the comments below.

If you try it, I would be genuinely curious to hear how it works for your field — what breaks, what you changed, what you wish it did differently.
The broader point I keep coming back to is this: the bottleneck for using these tools well is no longer technical ability. It is knowing what you want clearly enough to describe it. That is a clinical skill, not a programming one.
One last note: this article was written by Claude, based on my interactions with it during the build. I gave it the context, it found the words. If the style feels a little different from what you are used to reading from me, that is why. Which feels like a fitting way to end a post about AI as a practical research partner.
