# Module 2: Validate AI Opportunities and Technical Feasibility — Speaker Notes

Casual talking points for each slide. Not a script — just the key things to say and the energy to bring. Real examples from companies like Spotify, Amazon, Grammarly, and Samsung to ground every concept.

---

## Slide 1 — Title

Welcome to Module 2 — Validate AI Opportunities and Technical Feasibility. Last time you learned how to build with AI. Today we answer a harder question: should you build it at all? Let's get into it.


## Slide 2 — Class Expectations

Quick refresher on our ground rules. Cameras on — yes, still. Arrive on time, engage actively during exercises, and use Slack for all communication. If you've got a deep question that could derail us for 15 minutes, save it for after class — I'll stick around. Otherwise, jump in, participate, and connect with each other. The networking you do here is just as valuable as the content.


## Slide 3 — Syllabus

Here's where we sit in the course. Module 1 gave you the AI-first mindset and the mechanics of prompting. Today in Module 2, we level up from execution to strategy. You're becoming an AI strategist — someone who can look at a hundred possible AI features and pick the three that will actually move the business.

Modules 3 through 6 will take us deeper into RAG architecture, AI-native UX design, agentic systems, and evals. But none of that matters if you're building the wrong thing. That's why today is so critical.


## Slide 4 — Agenda

Four sections today. First, we figure out where AI actually fits in your product — spoiler: not everywhere. Second, we balance AI bets with autonomy — how much control do you give the machine versus the human? Third, we make product decisions based on technical needs — governance, responsible AI, and the real-world stakes of getting it wrong. And fourth, you'll build your AI Strategy One-Pager — the single most important artifact for getting buy-in from stakeholders.


## Slide 5 — Where Does AI Actually Fit In Your Product?

Section one. This is the question that separates good AI PMs from everyone else. The temptation is to put AI everywhere. Resist that temptation. Let's talk about where it actually belongs.


## Slide 6 — Fake Good vs. Boring Killer

I love this framework because it cuts through the hype instantly. There are two types of AI features in the wild:

"Fake Good" features — these are the shiny distractions. They look incredible in a demo. Your CEO sees them at a conference and says "we need that." But in practice, they provide little utility. Generic chatbots on every screen that hallucinate or go in circles. AI summary tools that just add more words to a document without actually synthesizing anything. Users try them once for the novelty, then never touch them again.

"Boring Killer" features — these are the silent workhorses. They solve unglamorous problems. They're not flashy, but they become essential. Automatic reconciliation logic that silently matches support tickets to CRM data. A copilot that reliably turns messy interview notes into structured PRD drafts. Nobody tweets about these features. But try removing them and watch what happens.

Zapier is a Boring Killer. Nobody shows it off at parties. But millions of people would lose their minds if it disappeared tomorrow. That's the energy you want for your AI features.


## Slide 7 — Instructor-Led Q&A: Fake Good or Boring Killer?

Let's make this real. Two questions for you:

First — in your own experience managing or using AI products, where has a flashy AI feature completely flopped? Think about a time you were excited about an AI feature, tried it, and went "...that's it?"

Second — where has a quiet automation become genuinely indispensable for you? Something you barely think about but would really miss if it vanished.

Feel free to unmute or post in the chat. I'll share mine too — I've seen both sides of this coin plenty of times.


## Slide 8 — Four Ways AI Creates Real Value

Once you've decided your feature is a Boring Killer and not a Shiny Distraction, you need to define the actual mechanics. There are four value propositions AI can deliver:

Personalization — adapt to each user in real time. Spotify's AI DJ doesn't just shuffle songs. It learns your taste, your mood, your listening patterns, and curates a unique experience. Netflix does the same with recommendations. The key is real-time adaptation, not static profiles.

Automation — remove manual, repetitive work entirely. Zapier connects your tools so you never have to copy-paste between apps again. Zendesk AI auto-routes and resolves common support tickets without a human touching them.

Augmentation — make humans 2-10x faster or smarter. GitHub Copilot doesn't replace developers — it makes them dramatically faster. Glean surfaces the information you need across all your company's tools. Salesforce Agentforce multiplies your sales team's capacity.

Insights — find patterns and signals in messy data. Gong analyzes sales calls to surface what top performers do differently. Tableau Pulse highlights anomalies you'd never spot manually. Fullstory shows you exactly where users struggle.

Pick your lane. Each one has different technical requirements, different UX patterns, and different success metrics.


## Slide 9 — The Three-Layer Model

This is your central mental model as an AI PM. Memorize it. Tattoo it on your brain. It's designed to stop you from "solutioning" — falling in love with a cool technology and then looking for a problem to justify it.

Layer 1: User Workflow — identify the specific job-to-be-done or friction point. Example: "A PM needs to synthesize 10 user interviews into a strategy doc." Start here, always.

Layer 2: Technical AI Solution — determine which approach (LLM, RAG, Agentic workflow, Multimodal) best addresses that specific step. Example: "Multimodal RAG to process transcripts and video screenshots."

Layer 3: Business Outcome — define the macro goal this bet moves. Example: "Reduce discovery cycle time from 5 days to 4 hours per feature."

You need a clean, straight line through all three layers. If you can't draw it, the bet isn't ready. Google's search team doesn't build AI features because AI is cool — they build them because they measurably improve search quality, which drives ad revenue. The line is always there.


## Slide 10 — Balancing AI Bets With Autonomy

Section two. Now that you know where AI fits, you need to decide how much power you give it. This is the autonomy question, and getting it wrong can be catastrophic.


## Slide 11 — Choosing Your Level of Autonomy

One of your most critical decisions as an AI PM is determining how much control you give the model versus how much you leave with the human. There's a spectrum:

Assist — the AI helps, but the human drives. Think of autocomplete. The AI suggests, you decide.

Copilot — the AI drafts, the human approves. GitHub Copilot writes code suggestions, but the developer reviews and accepts. Grammarly suggests rewrites, but you click "Apply."

Agent — the AI acts autonomously toward a goal. The human sets the destination, the agent figures out the path.

The question you should always ask: "What is the safest useful level here for this product?" Not the most impressive. Not the most autonomous. The safest useful level. Start there. You can always dial it up later.


## Slide 12 — Jobs x Risk x Autonomy Matrix

This is your primary tool for deciding where to set the autonomy dial. Picture a 2x2 matrix: Impact on one axis, Risk on the other.

High Impact, Low Risk — synthesizing 100+ raw feedback snippets into themes. Great candidate for an agent. Let it run. The worst case is a mediocre summary, and a human reviews the output anyway.

Low Impact, Low Risk — drafting routine stakeholder update emails. Good candidate for a copilot. The AI drafts, you glance and send. Low stakes either way.

High Impact, High Risk — auto-prioritizing your roadmap and changing live dates. Good candidate for assist only. You want the AI to surface recommendations, but a human makes the final call. Changing live dates autonomously could cause chaos.

Low Impact, High Risk — automated deletion of "inactive" user accounts. Don't build this. The risk-reward ratio is terrible. One bug deletes active users, and you've got a PR crisis on your hands.


## Slide 13 — Breakout Group Exercise: Mapping Juno's Strategic Bet

Back to your groups from Module 1. You're applying the Three-Layer Model to Juno's next opportunity: Automated Prioritization.

Here's your mission. Look at the RocketShip scenario and find a prioritization failure that feels familiar — opinion-driven roadmaps, evidence buried in documents, risks discovered too late. Match an AI capability to that failure and set the autonomy dial. Then answer: if this engine was live today, what's the one metric that proves it beat the old manual process?

You've got 25 minutes. Be ready to explain why your chosen AI capability is the most efficient fix, not just the flashiest one.


## Slide 14 — Strategic Scorecard: Which AI Bets Deserve Oxygen?

Not every AI bet deserves engineering resources. You need a cold, objective filter. This scorecard gives you one.

Score each bet from 1 to 5 across four dimensions:

Data Readiness — do you actually have the logs, documentation, and clean data to fuel this AI? A 1 means "we don't even have the data." A 5 means "clean, labeled, ready to go."

UX Complexity — how hard is it to design a trustworthy interface for this workflow? Sensitive workflows like healthcare or finance score high here.

Risk and Governance Load — what's the weight of regulatory, privacy, and reputational risks? Some bets need legal sign-off before you write a single line of code.

Potential Impact — will this move a core business metric? Revenue, retention, operational quality? If it won't show up on a dashboard that leadership cares about, it's probably not worth the investment.

High data readiness, low UX complexity, low governance load, high impact — that's your sweet spot. Everything else goes in the "maybe later" pile.


## Slide 15 — Break

Five-minute break. Stretch, hydrate, check your messages. We'll pick up with the heavy stuff when you're back.


## Slide 16 — Cameras On

Welcome back! Cameras on, please. Let's keep the energy up for the second half.


## Slide 17 — Making Product Decisions Based on Technical Needs

Section three. We're moving from strategy to governance. This is the part where we talk about what can go wrong — and why it's your job to prevent it before it happens.


## Slide 18 — Responsible AI: Your Strategic Guardrails

Governance isn't a "legal problem" you can punt to someone else. It's a core component of your product strategy. Four guardrails:

Human Oversight — the "Safety Valve." AI must support decisions, not finalize them. Unmonitored autonomy can lead to catastrophic outcomes. In 2023, a Belgian man tragically took his life after following advice from an unmonitored AI chatbot. That's not a hypothetical risk. That's a real consequence of shipping without guardrails.

Transparency — the "Disclosure Label." Clearly distinguish between human-verified and AI-generated content. CNET published AI-generated financial articles with factual errors. Their credibility took a massive hit once the lack of disclosure was revealed. Your users deserve to know when AI is talking to them.

Bias Awareness — the "Equity Filter." Actively audit your training data. Amazon scrapped an AI recruitment tool after it was found to penalize resumes containing the word "women's." The model learned from historical hiring data, which reflected historical biases. The AI didn't create the bias — it amplified it.

Privacy — the "Digital Vault." Public LLMs are not private. Samsung employees leaked trade secrets by pasting confidential source code into ChatGPT. That data became part of the model. Use only approved, secure environments for proprietary data.

These aren't nice-to-haves. They're ship-blockers.


## Slide 19 — Run Your Bets Through the Matrix

Before committing to a direction, pressure-test every AI bet. For each one, decide:

Approach — are you buying an off-the-shelf solution, calling an API, fine-tuning, or building RAG?

Candidate — which model or provider are you leaning toward?

Strategy — what infrastructure will you own versus outsource?

Safety — what are the key governance questions that need answers before you proceed?

This is a first-pass strategy, not a full architecture review. But it forces you to think through the real implications of your bet before you've burned engineering cycles.


## Slide 20 — Quick Debrief: Juno Strategic Pressure Test

Head to Slack. One sentence: looking at your chosen Juno bet, what is one high-stakes part of the workflow you would explicitly choose not to automate in v1, and why?

This is the discipline that separates great AI PMs from mediocre ones. Knowing what not to build is just as important as knowing what to build. The features you leave out of v1 aren't failures of imagination — they're evidence of strategic judgment.


## Slide 21 — AI Strategy One-Pager

Section four — the main event. Everything we've discussed today comes together in a single artifact: the AI Strategy One-Pager.


## Slide 22 — What Is an AI Strategy One-Pager?

Let me be very clear: this is not an idea deck. It's not a brainstorming document. It's a strategic tool designed to validate your product direction.

The biggest mistake PMs make is treating AI as a "blue-sky" brainstorming session. In reality, your leadership team is navigating intense market noise and they're rightfully skeptical of "magic AI" promises. The One-Pager is how you earn their trust.

It does three things: neutralizes skepticism with evidence, prioritizes limited engineering resources, and verifies your strategy can survive scrutiny. If your AI bet can't fill a single page compellingly, it's not ready for a roadmap.


## Slide 23 — Anatomy of the AI Strategy One-Pager

Six pillars, and I'll walk through each one using Grammarly as the example because their AI strategy is clean enough to reverse-engineer:

Problem & Workflow — define the specific friction point. "Professional writing is slow and prone to tone errors." Don't be vague. Pin it to a moment in the user's journey.

Target Metrics — what proves it's working? "Improved Time-to-Publish and Message Clarity Score." If you can't measure it, you can't defend it.

Autonomy Level — specify the interaction model. "Copilot: suggests rewrites but requires human approval to implement." This sets UX expectations for the entire team.

Data & Model Approach — your technical path. "Hybrid of general LLMs grounded with company-specific style guides via RAG." This is where engineering starts paying attention.

Risks & Mitigations — flag the one-way doors. "Risk of hallucinated facts; mitigated by focusing only on grammar and tone, not factual data." Be specific about what could go wrong and how you'll prevent it.

V1 Scope — what's in and what's out. "In: Tone and clarity edits. Out: Drafting legal contracts or autonomous sending." What the AI won't do is as critical as what it will do. This prevents scope creep and builds team trust.


## Slide 24 — Breakout Group Exercise: Build Juno's AI Strategy One-Pager

This is the big exercise. You're taking everything from today — the Three-Layer Model, the autonomy dial, the governance guardrails — and formalizing it into a One-Pager for Juno.

Focus on four things: what you're explicitly preventing (not just what you're building), proof that the bet is working, one clear one-way door risk you're willing to take plus the guardrail for it, and at least two high-risk actions that are strictly out of scope for v1.

You've got 30 minutes. This is where strategy gets real. The first exercise was theory — this is execution. Use your exercise guide.


## Slide 25 — Key Takeaways

Let me bring it home with a story about Spotify's Discover Weekly.

Back in 2015, Spotify's team had a hundred possible AI features they could build. Personalized playlists, auto-generated artist bios, AI-powered lyrics search, predictive skip detection — the list was endless. They could have chased all of them. Instead, they drew a straight line. The user friction: listeners were drowning in a 30-million-song catalog and couldn't find new music they loved. The technical solution: collaborative filtering combined with natural language processing on music blogs and reviews. The business outcome: increase weekly engagement and reduce churn by giving every user a reason to come back every Monday. One clean line through all three layers. That's takeaway one — the Three-Layer Model is your anchor. If you can't draw that straight line from friction to solution to outcome, stop building.

Now, Spotify could have gone fully autonomous — "Discover Weekly picks songs and auto-plays them all week, replacing your library." They didn't. They made it a curated playlist that refreshes once a week. The user still chooses to press play. They still skip songs. That feedback loop is what makes the system smarter. Spotify started with the safest useful level of autonomy and dialed up gradually — first Discover Weekly, then Daily Mixes, then the AI DJ. That's takeaway two — autonomy is a dial, not a switch. Start where trust is high and risk is low. You can always turn it up.

Here's what Spotify didn't build in v1: they didn't let the AI edit your existing playlists. They didn't auto-remove songs it thought you wouldn't like. They didn't replace the search bar with "just trust us." Those were deliberate boundaries — one-way doors they refused to walk through because the user trust wasn't there yet. That's takeaway three — defining what the AI won't do is as critical as defining what it will. Amazon's biased hiring AI, Samsung's leaked source code, CNET's hallucinated articles — they all forgot to set those boundaries.

And the reason Spotify's leadership greenlit Discover Weekly over a dozen competing ideas? The team had a clear, one-page case: here's the friction, here's the tech, here's how we'll measure success, here's what we're explicitly not doing, and here's the risk if we're wrong. That's takeaway four — the Strategy One-Pager aligns your entire team. It turns "I think we should try AI" into a defensible bet.


## Slide 26 — Extra Practice and Next Session

Two optional exercises:

First — map your own straight line. Take a high-friction workflow from your real job and draw the Three-Layer Model through it. Which AI capability fits? What business outcome proves it worked?

Second — set your personal autonomy dial. Pick a task you want to automate. Define the interaction model and list the specific kill-switch guardrails you'd need to trust it running without your constant oversight.

Next session is Module 3: Improve AI Product Requirements with RAG Architecture. You've learned to validate whether an AI bet is worth pursuing. Next, you'll learn how to ground that AI in real, proprietary data so it stops hallucinating and starts being useful. You'll master context engineering and write your AI PRD.


## Slide 27 — Resources and Templates

Here's the Module 2 Exercise Guide and any other resources you need. Bookmark them. They'll be handy as you refine your final project deliverables.


## Slide 28 — Q&A

Open floor. Any questions about today — the Three-Layer Model, the autonomy spectrum, responsible AI, the Strategy One-Pager? Unmute, drop it in chat, or save it for Slack. Let's hear it.


## Slide 29 — Thank You

Solid session today. You went from "how to build" to "what to build." That's a massive shift. See you next time!
