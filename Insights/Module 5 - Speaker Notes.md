# Module 5: Deploy Agentic Systems and Workflows — Speaker Notes

Casual talking points for each slide. Not a script — just the key things to say and the energy to bring. Real examples from companies like Cursor, Shopify, Uber, Stripe, and Johnson & Johnson to ground every concept.

---

## Slide 1 — Title

Welcome to Module 5 — Deploy Agentic Systems and Workflows. We've been building toward this. In Modules 1 through 4, AI was a conversational partner — you prompted, it responded. Today, AI becomes a delegatee. You set the goal, and the agent figures out the path. Let's go.


## Slide 2 — Class Expectations

You know the drill. Cameras on, be on time, participate, network, Slack for everything, deep questions after class. We're in the home stretch — two modules left. Let's make them count.


## Slide 3 — Syllabus

Quick check-in on where we are. Module 1: prompting and mindset. Module 2: strategy and validation. Module 3: RAG architecture and AI PRDs. Module 4: AI-native UX design. Today in Module 5, we make the jump from reactive AI to autonomous AI. This is the frontier.

You're moving from "I prompt the model and it responds" to "I define a goal and the agent decides how to achieve it." That's a fundamental shift in the human-AI relationship, and it comes with a whole new set of product challenges.


## Slide 4 — Presentation Reminder

Quick heads up — we're almost at the end of the course. Next session is your final class, and we're looking for 2-3 groups to volunteer and present their final project. This is optional but highly recommended. You'll get live, actionable feedback that's incredibly valuable. I'll ask for volunteers in the Slack channel today. First come, first serve.


## Slide 5 — Agenda

Three main sections plus an optional post-class lab. First, the shift to agentic orchestration — understanding what agents are and why they change everything. Second, agentic design patterns — the blueprints for how agents think and reason. Third, managing the agentic handoff — the Agent Workflow Spec, failure modes, and rules of engagement.


## Slide 6 — The Shift to Agentic Orchestration

Section one. We're about to cross a threshold. Everything you've built so far — prompts, RAG, UX — has been about making AI respond well. Agents are about making AI act well. Big difference.


## Slide 7 — From Answers to Judgment: The Evolution of Value

Let me frame the evolution you've been living through this course:

Chatbots provide answers based on a knowledge base. The user prompts, the AI responds. It's human-led — the user pulls value manually. This is where we started in Module 1.

Workflows provide execution of predefined steps across systems. The AI follows a rigid track and the human monitors the process. Human-supervised. Think of a Zapier automation that runs the same sequence every time.

Agents provide judgment for path choice based on real-time context. The user sets the goal, the agent autonomously navigates the how. Human-governed — not human-led, not human-supervised, but human-governed. The agent has latitude to make decisions within boundaries you set.

This changes the dynamic between your user and your product. When the AI just answers questions, you design for prompts. When the AI executes workflows, you design for steps. When the AI exercises judgment, you design for goals and guardrails. That's the new game.


## Slide 8 — What Is an Agent?

An agent is an intelligent system that interprets intent, makes decisions, and takes actions autonomously to achieve a goal. Three defining traits:

Proactive — it acts on environmental triggers without direct user prompts. It doesn't wait to be asked. When new data arrives, the agent starts processing.

Task-Oriented — it executes multi-step workflows to deliver finished outcomes. It doesn't give you ingredients — it cooks the meal.

Integrated — it connects with tool stacks to perform actions in the real world. It doesn't just talk — it does. It calls APIs, writes to databases, sends emails, creates tickets.

The key distinction from everything we've built before: a standard LLM is a reactive brain that waits for input. An agent is a proactive system that pursues goals.


## Slide 9 — The Anatomy of an Agent

To move from a chatbot to an agent, four pillars must be built into the system architecture:

The Reasoning Engine — the brain. This is the LLM, but upgraded from predicting text to predicting autonomous actions. It interprets the user's goal and decides what to do.

The Strategy Layer — the planning capability. Logic that deconstructs high-level goals into verifiable, multi-step execution plans. "Book a trip" becomes "1. Search flights, 2. Compare prices, 3. Book the cheapest, 4. Reserve hotel near the airport."

The Action Layer — the arms. The bridge connecting AI logic to existing product capabilities and APIs. Search tools, comparison tools, booking tools. Without this layer, the agent can think but can't do.

The Context Layer — the memory. Infrastructure that maintains task state over time. The agent remembers what it already searched, what the user prefers, what failed last time. Without memory, every interaction starts from zero.


## Slide 10 — The Agent Spectrum

In previous modules, you looked at autonomy as a list of capabilities. Now let's look at it through the lens of product risk. Four levels:

Level 0 — Reactive. No autonomy. The user prompts, the model responds. PM owns prompt quality and response accuracy. This is what you built in Module 1.

Level 1 — Function-Calling (Assisted Autonomy). The model can call specific tools — a calculator, a search API — but only when explicitly triggered. PM owns tool selection logic and fallback behaviors. "If the tool fails, what happens?"

Level 2 — Semi-Autonomous (Human-in-the-Loop). The agent plans and executes multi-step workflows, but pauses at checkpoints for human approval. PM owns checkpoint design and escalation paths. "When does the agent ask for permission?"

Level 3 — Fully Autonomous (Goal-Driven). The agent receives a goal and navigates the entire execution path independently. PM owns trust, system rollback, and auditability. "If the agent makes a bad decision at 3 AM, how do we recover?"

More autonomy means more accountability for you as the PM. Level 3 is exciting but the risk surface is enormous. Start where the risk is manageable.


## Slide 11 — Real-World Examples: How Companies Are Using Agents

Let's ground this in reality. Five companies deploying agents at scale:

Johnson & Johnson — Drug Discovery Agents. Lab agents optimize chemical synthesis by determining reaction conditions and accelerating processes that were traditionally manual. They leverage digital twins and machine learning for precision. This is Level 2-3 autonomy in a controlled scientific environment.

Uber — Support & Resolution Agents. Agents autonomously diagnose ride issues and fraud, gathering evidence, triggering refunds, and executing internal workflows. They escalate to humans only when confidence is low or policy requires it. Smart human-in-the-loop design.

Stripe — Financial Operations Agents. Agents investigate failed payments and regulatory compliance by retrieving policy context and analyzing transaction data. They recommend or execute financial next steps across fragmented systems. High-stakes, high-value.

Shopify — Merchant Operations Agents. Agents manage store setups and inventory by reasoning over merchant context and calling internal APIs. They resolve disputes and configure marketing campaigns. The merchant sets the goal, the agent handles the operational complexity.

Cursor — Developer Workflow Agents. Agents embedded in the IDE plan refactors and apply code edits across multiple files simultaneously. The developer validates the outcome, but the agent determines execution steps. You're literally using this pattern right now if you code with Cursor.


## Slide 12 — Quick Debrief: Juno's Autonomy Risk Statement

Head to Slack. In one sentence: identify one specific product problem that may appear when you move Juno from Level 1 (Assisted) to Level 2 (Semi-Autonomous) or Level 3 (Fully Autonomous) that didn't exist before.

This is the question every AI PM must answer. New capabilities create new failure modes. What risks does autonomy introduce that simple prompting never had? Reasoning drift? Silent failures? Actions the user didn't authorize? Name the risk now so you can design for it.


## Slide 13 — Agentic Design Patterns

Section two. You don't solve complex agentic problems with a better prompt. You solve them by choosing how the agent is wired to think. Patterns are your blueprints.


## Slide 14 — Why Patterns Matter

Two big reasons:

First, patterns provide a common vocabulary for your AI PRD. When you write "this agent uses a Planner-Executor pattern," your engineering team immediately knows the architecture. No ambiguity.

Second, patterns enforce a specific reasoning structure. They prevent the failure modes we'll discuss later — drift, infinite loops, silent failures. The pattern is the guard rail for the agent's thinking process.

You're moving from being a prompt writer to being a system architect. That's a meaningful evolution in your PM capabilities.


## Slide 15 — Pattern: ReAct (The Inner Monologue)

ReAct stands for Reason-Act-Observe. The agent that thinks before it acts.

The mechanism: the agent uses a continuous loop. Think ("I need to find the source"). Act (calls a search tool). Observe ("reads the API result — data found"). Then asks itself: "Does this answer the question?" If yes, deliver the final response. If no, loop again with a new thought.

The value: it solves high-variability problems by thinking out loud, creating a visible reasoning trace that makes debugging much easier. You can actually see why the agent made each decision.

The trade-off: every loop adds a latency tax. You're trading instant response times for higher task accuracy. For a quick lookup, ReAct is overkill. For a complex investigation — "why did revenue drop last quarter?" — it's exactly what you want.


## Slide 16 — Pattern: Planner-Executor (The Task Architect)

This pattern mimics a project manager and a specialist working together.

The mechanism: one "Planner" agent deconstructs a goal into a roadmap. A separate "Executor" agent processes the tasks. "Plan a trip" gets decomposed into "Book flight, Book hotel." The executor completes task 1, reports status, and the planner dispatches task 2.

The value: it prevents reasoning drift by keeping the high-level objective separate from the technical details. The planner stays "above the fray," focused only on the sequence. The executor stays focused on doing, not planning.

The trade-off: now you have two distinct reasoning chains to monitor. More powerful, but more complex. If the planner gives bad instructions, the executor will diligently do the wrong thing.


## Slide 17 — Types of Agentic Memory

Agents need different types of memory for different purposes — just like humans:

Contextual Memory — manages the immediate data and variables being processed right now. What's in the current working set? Think of it as your desk — what's in front of you at this moment.

Episodic Memory — tracks the sequence of actions taken within a specific task. What did the agent already try? What worked? What failed? This prevents the agent from repeating the same failed approach.

Semantic Memory — stores persistent behaviors, user preferences, and core system instructions. This is the agent's "personality" and "knowledge" that persists across sessions. "This user always prefers concise responses."

Linked Memory — accesses real-world systems and live databases via APIs. The agent doesn't store the data — it knows where to look it up. Your CRM, your analytics dashboard, your support system.

As a PM, you decide which memory types your agent needs and how long each persists. An agent that forgets user preferences every session is annoying. An agent that remembers too much raises privacy concerns.


## Slide 18 — Break

Five-minute break. Agent architecture is dense material. Give your brain a rest.


## Slide 19 — Cameras On

Welcome back! Cameras on. We've got the handoff section ahead — the practical stuff you'll use for your final project.


## Slide 20 — Managing the Agentic Handoff

Section three. You've got the concepts and the patterns. Now let's talk about how you actually hand this to engineering in a structured, buildable format.


## Slide 21 — The Agent Workflow Spec (AWSpec)

Think of the AWSpec as the technical addendum to your AI PRD — specifically designed for agentic features. While the PRD defines the user experience, the AWSpec defines the autonomous system logic.

Four sections:

Actors — who's in the loop? Define which agents, tools, and humans are involved. Be explicit about who's the pilot and where the human must step in as a mandatory decision-maker. "Juno is the primary agent. The PM reviews all priority changes above P1."

Pattern Plan — which reasoning pattern(s) will be used? Map the key sequential steps from user intent to final outcome. "ReAct for initial analysis, Planner-Executor for multi-document synthesis."

Memory — what persists across the session? Specify what needs to be in working memory versus historical context. "Current transcript stays in working memory. User's team preferences persist in semantic memory."

Tools — which APIs and databases is the agent authorized to call? Define the schemas and Read/Write boundaries. "Read access to the CRM and Jira. Write access limited to creating draft tickets — no direct publishing."

This is your one-page blueprint for engineering. Without it, they're guessing at the architecture.


## Slide 22 — Breakout Group Exercise: Write Your AWSpec for Juno

Back to your groups. You're writing the autonomous system logic required to transition Juno from a static prototype to a functional product agent.

Map out: Actors (roles for Juno, any sub-agents, and the user), Plan (core pattern and sequential steps), Memory (persistence policy for carrying context), and Tools (API schemas and read/write boundaries).

Align everything with your Module 3 AI PRD. This is the engineering handoff document — make it tight. Add the completed AWSpec into your final project deliverables deck. You've got 30 minutes.


## Slide 23 — The Orchestration Gap: Common Failure Modes

Here's where agents break in production. Four failure modes you need to know:

Silent Failures — when a tool returns "No data," the agent may falsely assume the task is complete instead of checking its logic. It silently moves on, and the user gets an incomplete answer without any warning. This is the sneakiest failure mode because nobody notices until the damage is done.

Reasoning Drift — after multiple loops, the agent can lose its "north star" and start solving for the wrong sub-task. It's like a researcher who goes down a rabbit hole and forgets the original question. The more loops, the more drift risk.

Infinite Loops — the agent gets stuck in a thought-action cycle, repeatedly trying a failing tool without recognizing a dead end. It's the AI equivalent of "have you tried turning it off and on again" — except it never stops trying.

The Latency Tax — each autonomous reasoning step adds cumulative seconds. A 5-step loop can force a user to wait 40+ seconds for a result. That's an eternity in a product experience.

You don't fix these with a better prompt. You fix them with architectural guardrails.


## Slide 24 — A PM's Agent Control Panel

Four controls you need to build into every agent:

Define Stop Conditions — set the maximum number of steps to prevent infinite loops and cost overruns. "After 5 retrieval attempts, stop and return the best available answer with a confidence warning."

Structure Tool Outputs — partner with engineering to ensure APIs return clear, structured responses. Vague outputs cause hallucinations. If a tool returns "Error," the agent needs to know what kind of error and how to handle it.

Set Confidence Thresholds — define when the agent's internal uncertainty triggers a human-in-the-loop review. "If confidence drops below 70%, pause and ask the user to confirm before proceeding."

Manage the North Star — provide system instructions that the agent re-reads in every loop to prevent reasoning drift. This is the agent's constant reminder of what it's actually trying to accomplish.


## Slide 25 — Defining the Rules of Engagement

Agents fail by policy and design, not just intelligence. Four rules you must define:

Agency Permission — you define the autonomy threshold. "The agent can draft a $5k quote but cannot hit Send." Be precise about what actions the agent can take independently versus what requires human approval.

Access Control — you define read/write boundaries for every tool and database. "The agent can read the HR handbook but cannot edit payroll." This prevents catastrophic actions even if the reasoning is wrong.

Fallback Protocols — you specify what happens when things break. "After 3 failed attempts to resolve, the agent must escalate to a human." Don't let the agent silently fail.

Checkpoints — you set red-zone triggers for human intervention based on risk, value, or ambiguity. "Any legal policy changes require a human moderator's signature." This is your safety net for high-stakes decisions.


## Slide 26 — The PM Decision Triangle

As the PM, you're the "optimizer-in-chief." Engineering always wants the most accurate agent. Your job is to make it fit the business constraints. Three corners of the triangle:

Accuracy (Quality/Reasoning) — achieved through reflection patterns and multi-step planning. Maximizes quality but adds latency and cost.

Latency (Speed/UX) — achieved through single-pass execution, routing, and smaller models. Maximizes speed but sacrifices reasoning depth.

Cost (Efficiency/ROI) — achieved through open-source models, prompt caching, and slimmer context. Minimizes spend but may limit capability.

You can't maximize all three. Pick the two that matter most for your specific use case and accept the trade-off on the third. A customer support agent prioritizes latency and cost. A medical diagnosis agent prioritizes accuracy and latency. A research agent prioritizes accuracy and cost.


## Slide 27 — Key Takeaways

Let me bring it home with a story about Uber.

Uber's support system used to be mostly human-powered. A rider reports a bad trip — wrong route, safety concern, payment dispute. A human agent reads the complaint, pulls up the trip data, checks driver history, reviews payment logs, and decides on a resolution. It worked, but at millions of tickets a week, it didn't scale.

So Uber built real support agents — not chatbots, but systems that diagnose problems autonomously. The agent reads the complaint, pulls GPS data, checks if the route deviated, reviews driver ratings, cross-references payments, and makes a call: issue a credit, flag the driver, or escalate to a human. The rider sees "We've reviewed your trip and issued a credit." Behind the scenes, six decisions in three seconds. That's takeaway one — you're not writing prompts anymore. You're designing goals and guardrails for a system that exercises judgment.

Those agents needed architecture. A reasoning engine to interpret the complaint, a strategy layer to decompose it into steps, an action layer to call the trip API and payment system, and a context layer that remembers this rider had the same issue two weeks ago. Remove any pillar and it breaks. No memory? It re-investigates the same issue from scratch. No tools? It can reason but can't check the data. That's takeaway two — agent anatomy requires all four layers. You're the architect ensuring each one is in place.

Uber didn't use one pattern for everything. Simple "where's my receipt?" queries use a ReAct loop — think, search, respond. Complex fraud investigations use Planner-Executor — one agent plans the steps, another executes them. A routing layer at the front decides which pattern to use. That's takeaway three — picking the right agentic pattern for the right task is how you balance accuracy, cost, and speed.

And what keeps it safe: the agent can issue refunds up to $10 autonomously. Over $10 requires human approval. Safety complaints always escalate — no exceptions. The agent has read access to trip data but write access only for credits and tickets — it can never modify a driver's account. After three failed attempts, it stops. Every decision is logged. That document — the one defining stop conditions, access boundaries, and human checkpoints — is the AWSpec. That's takeaway four — without the AWSpec, you're hoping the agent behaves. With it, you're ensuring it does.


## Slide 28 — Extra Practice and Next Session

Two optional exercises:

First — try building the Juno agent in Langflow using the exercise guide. Get your hands on the actual architecture.

Second — select a workflow where your current AI solutions suffer from reasoning drift or silent failures. Design a requirement that applies a Reflection or Planner-Executor pattern to force a self-correction loop.

Next session is Module 6: Measure AI Quality with Evals and Guardrails. This is the final module. You'll learn to replace vibe checks with systematic evaluation — the last piece of the puzzle. And we'll have the optional project showcase for volunteer groups. Make sure to volunteer in Slack if you want live feedback on your final project.


## Slide 29 — Resources and Templates

Module 5 Exercise Guide is here. Bookmark it for reference, especially the AWSpec template.


## Slide 30 — Q&A

Open floor. Questions about agents, patterns, the orchestration gap, the AWSpec, the decision triangle? Let's hear them. Unmute, chat, or Slack.


## Slide 31 — Optional Post-Class Lab: Build Juno's Agentic Workflow in Langflow

For those who want hands-on practice with actual agent architecture, there's an optional lab using Langflow. This is where you build the pipeline visually — drag components, connect nodes, see the agent think.


## Slide 32 — Lab Setup Instructions

Download the JSON file linked in the exercise guide, create a new blank flow in Langflow, and drag the JSON onto the canvas. It preloads the architecture but not your API keys — you'll need to add those. Follow the walkthrough guide for the full setup.


## Slide 33 — Thank You

Incredible session. You went from "AI responds to my prompts" to "I design autonomous systems that make decisions within guardrails I define." That's a career-level skill. One more module to go. See you next time!
