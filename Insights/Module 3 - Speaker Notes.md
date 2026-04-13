# Module 3: Improve AI Product Requirements with RAG Architecture — Speaker Notes

Casual talking points for each slide. Not a script — just the key things to say and the energy to bring. Real examples from companies like Google, Notion, Stripe, and Perplexity to ground every concept.

---

## Slide 1 — Title

Welcome to Module 3 — Improve AI Product Requirements with RAG Architecture. In Module 1, you learned to prompt. In Module 2, you learned to strategize. Today, you learn to ground your AI in real data. This is where prototypes become products.


## Slide 2 — Class Expectations

Quick ground rules reminder. Cameras on, arrive on time, participate actively, connect with your peers, use Slack, and save deep questions for after class. You know the drill by now. Let's keep the momentum going.


## Slide 3 — Syllabus

We're at the halfway mark. Module 1 gave you the AI-first mindset and prompting skills. Module 2 taught you to validate your AI bets with the Three-Layer Model and Strategy One-Pager. Today in Module 3, we bridge the gap between product specs and actual AI systems. You're going to understand how RAG — Retrieval-Augmented Generation — works, and more importantly, how to write product requirements for it.

This is where a lot of PMs get uncomfortable because it feels "too technical." It's not. You don't need to build the pipeline yourself. You need to know enough to write requirements that engineering can actually execute on. That's what today is about.


## Slide 4 — Agenda

Four sections. First, the power of context and context engineering — why prompting alone isn't enough. Second, hands-on lab — you'll upgrade Juno with RAG capabilities in Lovable. Third, mapping RAG to your AI PRD — translating technical architecture into product requirements. Fourth, RAG costs, control, and trade-offs — the decisions you'll make with your engineering lead.


## Slide 5 — The Power of Context and Context Engineering

Section one. We're going to expand your toolkit from prompt engineering to context engineering. Think of prompt engineering as telling the AI what to do. Context engineering is giving it the right information to do it well.


## Slide 6 — Prompt Engineering vs. Context Engineering

In Modules 1 and 2, you learned prompt engineering — instructions, formatting, wording. Your levers were system prompts, few-shot examples, and hyperparameters. That's great for fast UX experimentation and early-stage prototyping. But it struggles with factual grounding and scaling across proprietary data. You can't prompt your way to accuracy when the model doesn't have access to the facts.

Context engineering is the next level. It focuses on designing data inputs — documents, chunks, and metadata. Your levers are ingestion, chunking, embeddings, and vector search. It gives you high reliability, maintainability, and cost control. The trade-off? More architectural complexity and higher initial latency.

You need both skills to be an effective AI PM. But context engineering is where AI systems become "real products." It's the difference between a chatbot that guesses and a copilot that cites its sources.

Think of it like a lawyer. Prompt engineering is like telling the lawyer "be persuasive." Context engineering is like handing the lawyer the right case files, precedents, and evidence. The best lawyer in the world can't win a case without the right documents.


## Slide 7 — RAG Process Overview

RAG stands for Retrieval-Augmented Generation. It's a three-step process that combines an LLM with a targeted search over your own proprietary data.

Step 1: Retrieve — before answering, the model searches a defined knowledge base to find relevant context. It doesn't guess from training data. It goes and looks for actual information.

Step 2: Augment — within the knowledge base, it finds the most relevant information to help complete the task. This is the filtering step — separating signal from noise.

Step 3: Generate — the model uses the retrieved context, combined with the user's original query, to generate a factually grounded answer.

Here's the critical insight: the quality of the final answer depends entirely on how well you've curated the library it's searching from. If you feed it garbage data, you get garbage answers with confident citations. That's actually worse than hallucinating, because now the user trusts the wrong answer.

Perplexity is a great public example. When you search on Perplexity, it doesn't just generate an answer from its training data. It retrieves real sources from the web, synthesizes them, and provides citations. That's RAG in action.


## Slide 8 — How RAG Works in Practice

Let's get into the mechanics. Before the three-step loop runs, there's a Step 0 — data preparation. This is the offline process of building the knowledge base.

Raw data sources — documents, PDFs, web pages, support tickets — get processed through information extraction (OCR, PDF parsing, web crawlers). Then they're chunked — broken into smaller pieces the model can actually digest. Those chunks get embedded — turned into mathematical vectors that capture meaning. And those vectors get stored in a vector database.

When a user sends a query, that query also gets embedded. The system finds the most similar vectors in the database (that's the Retrieve step), packages the relevant chunks into the prompt (Augment), and the LLM generates a grounded response (Generate).

As a PM, you don't need to build this pipeline. But you absolutely need to understand it because every decision in this chain — what data to include, how to chunk it, how many chunks to retrieve — affects your product's quality, cost, and speed. Those are product decisions, not just engineering decisions.


## Slide 9 — Instructor-Led Q&A: RAG In Your Workplace

Quick question for the group: what is one messy set of documents or workflows you wish you could "talk to" using this exact method of RAG?

Think about your daily work. Is it a pile of user research transcripts? Your company's internal wiki that nobody can navigate? A folder of legal contracts? A backlog of support tickets?

This is meant to anchor the technical architecture to a real pain point you actually feel. Feel free to unmute or drop it in the chat.


## Slide 10 — Hands-On Lab: Improve Juno's Capabilities with RAG

Lab time. You're going back to your Juno prototype in Lovable and adding the RAG architecture. This is where your copilot stops being a "dumb UI" and starts being a judgment engine.


## Slide 11 — Lab Exercise Outcome Preview

Here's a quick preview of what you'll build. By the end of this exercise, Juno won't just process raw transcripts — it will cross-reference them against RocketShip's internal strategy to produce contextually grounded prioritization. This is a significant upgrade from Module 1's prototype.


## Slide 12 — Lab Exercise: Improve Juno's Capabilities with RAG

Here's the step-by-step. Open your existing Juno project in Lovable. Paste Artifact 1 into your Raw Insights column to re-establish a baseline.

Then refactor the dashboard for strategy ingestion by pasting the "RAG Refactor Prompt." This evolves your UI to accept strategic context alongside raw data.

Next, enable RAG logic and cloud processing by pasting the "Logic Ingestion Prompt." When Lovable asks you to approve cloud access, click Approve. This connects your UI to a real AI backend.

Finally, paste the RocketShip Strategy One-Pager text into your new strategy column and re-process the transcript. Watch what happens. Juno's priorities should shift to align with company goals, and it should explicitly cite your strategy document to defend its reasoning.

This is the "aha" moment. Before RAG, Juno gave generic analysis. After RAG, Juno gives grounded analysis that references your actual strategy. That's the difference between a toy and a tool.

You've got 30 minutes. Follow along with me in real time.


## Slide 13 — Quick Debrief: Improving Juno's Capabilities Statement

Head to Slack. In one sentence: what surprised you the most about the RAG experience in Lovable, and what was your biggest takeaway?

For most people, the surprise is how dramatically the output quality changes when you give the model real context. It goes from "plausible but generic" to "specific and defensible." That shift is what RAG is all about.


## Slide 14 — Mapping RAG To Your AI PRD

Section three. You've seen RAG in action. Now let's talk about how you specify it as a product requirement. This is where you stop being the PM who says "add RAG" in a Slack message and become the PM who writes precise technical requirements that engineering can actually build from.


## Slide 15 — What's New in an AI PRD?

A traditional PRD is about features. An AI PRD is about performance and trust. Beyond standard user stories, you need seven new sections:

Model Requirements — specify the provider, context window limits, latency targets, modality, and the choice between open or proprietary models.

Data Requirements — define what data sources you'll use for grounding, the preparation process (chunking, metadata tagging), and refresh cadence.

Prompt Requirements — outline the system prompt instructions, prohibited content guardrails, and behavioral constraints like brand voice.

AI User Experience — focus on building trust through citations, confidence signals, and user education about AI capabilities and limitations.

AI Testing & Measurement — establish a validation plan using a Golden Dataset as ground truth. Define thresholds for accuracy, bias, and robustness.

AI Risks & Mitigations — identify failure modes like PII leakage or model drift. Set "Hard Eval Gates" to block releases if safety thresholds aren't met.

AI Costs & Latency — forecast operational expenses based on token usage and development costs for data acquisition.

This might feel like a lot. It is. But each section prevents a specific class of failure. Skip the Data Requirements section and your RAG retrieves outdated garbage. Skip the Costs section and your product blows through its API budget in week one.


## Slide 16 — How to Incorporate RAG into Your Requirements

Let's connect each phase of the RAG pipeline to specific sections of your AI PRD.

Data Preparation (Step 0) — this goes in your Data Requirements section. Define which repositories the AI is allowed to access and how frequently the data must be updated. Example: "The system must sync with the Legal Department's repository every 4 hours."

Retrieve (Step 1) — this goes in your Model Requirements. Mandate the search strategy. Example: "The system must use Hybrid Search to recognize both exact product SKU codes and natural language queries like 'shipping delays.'"

Augment (Step 2) — this goes in your AI Costs & Latency section. Set the "Top-K" limit — the number of document chunks the AI reviews before answering. Example: "The retrieval loop must be limited to the top 5 segments to maintain response latency under 2 seconds."

Generate (Step 3) — this goes in your AI User Experience section. Mandate grounded trust. Example: "Every output must include a verifiable source link. If no data is retrieved, the AI must state it cannot find the information rather than guessing."

This is the product manager's contribution to RAG. You're not building the pipeline — you're defining the rules it operates by.


## Slide 17 — The Three Key RAG Trade-offs

As with everything in product management, there are trade-offs. Three big ones:

Accuracy vs. Cost — higher Top-K retrieves more document segments, which improves factual integrity. But more segments mean more tokens in the prompt, which drives up cost. You're essentially choosing between a thorough researcher who's expensive and a quick-glance assistant who's cheap.

Latency vs. Reasoning Time — smaller models or fewer retrieval steps give you faster response times. But smaller models may struggle with complex logic. It's the difference between instant autocomplete and a 10-second deep analysis. Both are valid — it depends on the use case.

Control vs. Implementation Speed — building custom, self-hosted infrastructure gives you full data sovereignty and privacy. But the engineering overhead is massive and slows your time-to-market. Using an off-the-shelf solution gets you there fast, but you're trusting a third party with your data.

Your job as a PM is to make these calls explicitly in the AI PRD, not leave them as implicit assumptions for engineering to figure out.


## Slide 18 — Break

Five-minute break. This was dense. Give your brain a rest. Grab some water.


## Slide 19 — Cameras On

Welcome back! Cameras on, let's finish strong.


## Slide 20 — RAG Costs, Control, and Trade-offs

Section four. We're going deeper into the economics and physics of RAG. This is the stuff you need to know when you sit down with your engineering lead and they start asking "which costs are you willing to optimize?"


## Slide 21 — Data Preparation: The PM's Responsibilities

Data preparation is about deciding what the AI is actually allowed to know. Three main responsibilities:

Define the authoritative source of truth — which documents represent the "truth" to prevent the AI from contradicting itself? If your pricing page says one thing and an old wiki page says another, the AI needs to know which one wins.

Decide freshness requirements — how quickly does your data change, and how often should the knowledge base update? A support knowledge base might need daily syncs. A legal policy base might need hourly. A product catalog during a sale might need real-time updates.

Capture ingestion rules in your AI PRD — taxonomy, data types, access controls. Who is authorized to view specific documents through the AI interface? External customers shouldn't see internal pricing strategies, even if they're in the same knowledge base.

These are product decisions, not ops decisions. Own them.


## Slide 22 — Augmentation Considerations

Augmentation is where you shift from the wording of prompt engineering to the data design of context engineering. You're deciding exactly which facts get packaged into the prompt.

Three levers: Filters define hard rules for metadata — the AI should never retrieve restricted or outdated data. Top-K specifies how many document segments to include — high for deep synthesis, low for fast production queries. Re-Ranking tells the system how to prioritize conflicting information — the most authoritative sources should appear first.

These translate directly into your Model and Data Requirements in the AI PRD. You're specifying the "physics" of the prompt window to prevent hallucinations and manage token costs.


## Slide 23 — Tokens and Context Windows

To own the cost and latency trade-offs, you need to understand the physics.

A token is the fundamental unit of compute. Every word, every piece of punctuation gets tokenized. Your cost per query is the sum of tokens in the prompt, the context retrieved via RAG, and the generated response.

A context window is the model's "short-term memory" limit for a single session. Think of it like a desk. A bigger desk lets you spread out more documents, but at some point the desk gets cluttered and you lose things. Models literally lose information buried in the middle of a long context window — that's called the "lost in the middle" problem.

Your Top-K requirements directly manage this. By limiting how many document segments you stuff into the context window, you keep costs down and prevent the model from missing critical information that gets buried.


## Slide 24 — Choosing Your RAG Architecture

Three architectural options:

Long Context Only — use a large frontier model that processes all relevant documents directly in a massive context window. Best when speed to prototype matters and data volume is limited. Downside: high token costs and the "lost in the middle" problem.

RAG — use a mid-sized model with a vector database that retrieves only the most relevant segments per query. Best when accuracy, citations, and cost predictability matter. Downside: higher upfront engineering complexity.

Hybrid — RAG identifies the correct files, then a large context window lets the model read those specific results in full. Best for mature products that need both global search and deep document reasoning. Downside: increased system complexity and higher latency.

Your choice depends on where you are in the product lifecycle, your data volume, and which trade-offs your business can tolerate.


## Slide 25 — Architecture Decision Factors

Three factors to guide your choice:

The "Where" of your data — if your data changes hourly, use RAG (just update the index). If you have a fixed set of documents where relationships across sections matter, long context might be better.

The "How" of the user task — if users ask targeted questions like "What was the SKU for the October order?", RAG with source links is ideal. If they need holistic analysis like "Compare the tone of these three 50-page scripts," long context shines.

The "Scale" of the product — massive knowledge bases with 10,000+ documents physically can't fit in a context window. RAG is the only option. Focused sessions where users upload a few documents? Long context or hybrid works great.

When your engineering lead asks "which architecture?", these three questions get you to the answer.


## Slide 26 — Breakout Group Exercise: Specifying Juno's Architecture in Your AI PRD

Final group exercise. You're completing AI PRD sections that specify Juno's exact RAG architecture and retrieval logic.

Four deliverables: Data Requirements — define your RAG knowledge base, data quantity, and update frequency. Model Requirements — select your retrieval strategy. AI Costs & Latency — use Top-K to manage the retrieval loop. AI User Experience — specify how Juno presents sources and handles missing evidence.

Align everything with your Strategy One-Pager from Module 2. You've got 30 minutes. Make it tight.


## Slide 27 — Key Takeaways

Let me bring it home with a story about Notion AI.

When Notion launched their AI features, the early versions were basically ChatGPT inside a text editor. You could ask it to summarize a page or brainstorm ideas, and it would generate something plausible — but generic. It didn't know your company's terminology, your project context, or what was in your other 500 pages. It was a smart stranger guessing. Users tried it, thought "that's cute," and went back to doing things manually. The moment everything changed was when Notion connected the AI to your actual workspace — your documents, your wikis, your project databases. Now when you ask "What's the status of Project Alpha?", it doesn't guess. It retrieves the specific page, reads the latest update, and gives you a grounded answer with a link back to the source. That's takeaway one — context engineering is where prompts become products. Designing what data the AI can access, how it's chunked, and how it's retrieved is what turns a novelty into a tool people depend on.

But Notion's team couldn't just flip a switch and say "index everything." They had to make precise decisions. Which workspace content gets indexed? How do you chunk a 10,000-word strategy doc so the AI retrieves the right paragraph, not a random one? How do you tag metadata so a question about "Q3 budget" pulls from the finance folder, not someone's meeting notes that happen to mention Q3? Those details went into their technical requirements — not vague hand-waves, but specific rules engineering could build from. That's takeaway two — your AI PRD must define precise ingestion, chunking, and metadata rules. Without them, engineering is guessing and your AI retrieves garbage.

Now here's the tension Notion had to navigate. Indexing more content means better answers — but also higher token costs and slower responses. Retrieving 20 document chunks gives you thoroughness but adds latency and expense. Retrieving 3 chunks is fast and cheap but might miss critical context. And building their own retrieval infrastructure gives them full control over user data, but it's a massive engineering lift versus using an off-the-shelf solution. That's takeaway three — every RAG trade-off is a product decision. Accuracy vs. cost, latency vs. reasoning, control vs. speed. You make these calls explicitly, not by accident.

And those choices compound. Notion chose a hybrid approach — RAG for targeted lookups across your workspace, long context for when you're working within a single large document. That architecture decision shaped their cost structure, their accuracy ceiling, and their ability to scale to millions of workspaces. That's takeaway four — your architecture choice dictates long-term viability. Get it right early, because switching later is expensive.


## Slide 28 — Extra Practice and Next Session

Two optional exercises:

First — identify a high-value knowledge source from your actual job (your team's PRD folder, API docs, or customer transcripts) and rewrite a system prompt with citations and grounding. Define your Top-K to prevent hallucinations.

Second — draft a "Model & Data" requirement snippet for a feature you're actually planning. Use the four sections from today (Data, Model, Costs, UX) to spec out a RAG-backed feature.

Next session is Module 4: Design AI-Native User Experiences. You've got the strategy and the architecture. Now you'll learn how to design interfaces that feel magical without sacrificing trust. You'll master invisible UI, intent-driven design, and the AI "Iceberg" — where the best experiences hide the complexity underwater.


## Slide 29 — Resources and Templates

Here's the Module 3 Exercise Guide and the AI PRD Template. Bookmark them. The PRD template especially is something you'll use far beyond this course.


## Slide 30 — Q&A

Any questions? We covered a lot of ground today — context engineering, RAG mechanics, AI PRDs, architectural trade-offs. If something's fuzzy, now's the time. Unmute, chat, or save it for Slack.


## Slide 31 — Thank You

Great work today. You went from "I can prompt an AI" to "I can specify how an AI system retrieves, processes, and presents real data." That's a major level-up. See you next time!
