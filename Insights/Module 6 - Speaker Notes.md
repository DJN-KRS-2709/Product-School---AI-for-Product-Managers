# Module 6: Measure AI Quality with Evals and Guardrails — Speaker Notes

Casual talking points for each slide. Not a script — just the key things to say and the energy to bring. Real examples from companies like Google, OpenAI, Stripe, and Netflix to ground every concept.

---

## Slide 1 — Title

Welcome to Module 6 — Measure AI Quality with Evals and Guardrails. This is the final module. You've learned to prompt, strategize, architect, design, and deploy agents. Now you learn to measure whether any of it actually works. This is where you close the loop.


## Slide 2 — Class Expectations

Last time with the ground rules. Cameras on, be on time, engage, connect with each other, Slack for everything, deep questions after class. This is the capstone — let's make it memorable.


## Slide 3 — Syllabus

Let's look at the full arc one more time. Module 1: the AI-first mindset and prompting. Module 2: strategy and validation. Module 3: RAG and AI PRDs. Module 4: AI-native UX. Module 5: agentic systems and workflows. And now Module 6: the measurement layer that holds everything accountable.

Here's the thing — everything you've built across five modules is impressive. But without measurement, it's just a collection of really good demos. Evals are what turn demos into products you can actually trust and ship.


## Slide 4 — Agenda

Four sections. First, production-grade evaluation requirements — why "vibe checks" fail and what replaces them. Second, measuring AI-powered product outputs — the three-layer eval stack. Third, AI levers for output optimization — what you tweak when the evals say "not good enough." And fourth, the group project showcase — your moment to present what you've built.


## Slide 5 — Production-Grade Evaluation Requirements

Section one. Let's talk about why "it looks good to me" is the most dangerous sentence in AI product management.


## Slide 6 — Why "Vibe Checks" Fail in Production

Three reasons vibe checks don't scale:

The Performance Gap — a single successful output proves the AI can do the task. It does not prove it will do so reliably across 1,000 different intents. You ran a prompt that worked beautifully in a demo. Then a user typed something slightly different and got complete nonsense. The demo didn't predict the failure because you never tested for variety.

Invisible Failures — without systematic measurement, high-stakes hallucinations and edge cases stay hidden until they reach the end user. The scary thing about AI failures is that they look confident. The model doesn't say "I'm guessing." It presents fabricated information with the same tone as verified facts.

The Subjectivity Trap — "Does this look good?" creates a vibe check culture where quality is whatever the last person to review it says it is. You can't make a data-driven Go/No-Go launch decision on subjective impressions. And you can't prove to leadership that your AI is improving without numbers.

Trust is earned through consistent, measurable performance. Not through a curated set of cherry-picked successes.


## Slide 7 — The 95% Accuracy Trap

Here's a trap that catches a lot of teams. Your model scores 95% on a benchmark. Celebration, right? Not necessarily.

Lab metrics — accuracy, precision, recall, F1 scores — are excellent for static datasets in controlled environments. But they're blind to the friction that matters in real products: latency, bias, inconsistency, trust erosion.

A "95% accurate" model still fails 5% of the time. If that 5% includes cases where it gives a customer incorrect legal advice, recommends the wrong medication, or leaks PII, your benchmark score is meaningless.

Evals look beyond lab scores to measure what actually matters: user experience, trust, and safety. Does the user trust the output? Does the AI handle edge cases gracefully? Does it degrade safely when it's uncertain? Those are product questions, not academic ones.


## Slide 8 — Measuring AI-Powered Product Outputs

Section two. Let's build your eval stack — the multi-layered measurement system that actually catches failures before your users do.


## Slide 9 — The AI Eval Stack

Three layers, each catching different types of problems:

Layer 1 — Automated Assessment (Component Level Evals). Machine-detectable tests that filter obvious failures, check formatting, and measure technical metrics like speed and accuracy at scale. These run fast and cheap. Think of them as the first filter — catching the easy stuff so humans don't waste time on it.

Layer 2 — Human Evals (System Level Evals). Experts using structured rubrics to judge nuance, tone, and helpfulness. Humans provide the calibration that machines can't. A model might score perfectly on accuracy but sound completely wrong for your brand voice. Only a human catches that.

Layer 3 — User Feedback (Online Evals). The final reality check. Production data like regeneration rates, task completion rates, and thumbs-up/thumbs-down signals confirm whether the product is actually delivering value. The users have the final vote.

You need all three. Automated alone misses nuance. Human alone doesn't scale. User feedback alone comes too late. Together, they form a complete safety net.


## Slide 10 — How to Build a Human Eval Rubric

Think of this like building a grading rubric for a college course. Five steps:

Step 1 — Define your Value Proposition. What user needs and product promises must the AI fulfill? "Juno must save PMs time by producing accurate, evidence-backed priority recommendations."

Step 2 — Define Evaluation Criteria. What specific dimensions measure those promises? Factuality, tone, logic, completeness, source accuracy.

Step 3 — Create Scalable Questions. Turn qualitative vibes into quantitative data. Binary yes/no: "Did the output cite at least one source?" Or 1-5 scale: "Rate the logical coherence of the prioritization reasoning."

Step 4 — Calibrate Reviewers. Create prototypical assessments so all reviewers are trained on the same expectations. If three reviewers score the same output differently, your rubric isn't clear enough.

Step 5 — Continually Validate. Have reviewers justify their ratings to surface edge cases and rubric drift. The rubric evolves as the product evolves.

The goal: convert subjective human judgment into an objective, system-level signal that identifies launch blockers.


## Slide 11 — Real-World Example: Human Evaluation at Google Assistant

Google was building a human-in-the-loop personal assistant that combined humans and AI to fulfill complex tasks. They needed to assess task fulfillment quality — not just "did it work?" but "how well did it work?"

Their rubric had 26 questions covering simple technical criteria, specific desired outcomes, and subjective human evaluations. It was calibrated across Product, UX, and UX Research teams, then used to train a dedicated team of manual reviewers.

After each conversation, the transcript was sent to a reviewer who evaluated end-to-end performance against the rubric. The data identified specific failure modes — not vague "it's not great" feedback, but precise "Step 3 fails when the user provides ambiguous location data" insights.

That's the power of structured evaluation. It turns "something feels off" into "here's exactly what's broken and here's how to fix it."


## Slide 12 — The PM's Role in Evaluations

Three main responsibilities:

First — you draft the definition of quality. In traditional software, the code defines the correct answer. In AI, quality is a spectrum, and you set the bar. Your primary deliverable isn't a feature spec — it's a rubric that defines what a "perfect" response looks like for your specific user.

Second — you set the pass thresholds. You decide the acceptability gap. Work with engineering to determine which failure modes are minor annoyances (tone slightly off) versus launch blockers (hallucinated data in a financial summary). Not all failures are equal.

Third — you audit the automated judges. If you're using "LLM-as-a-judge" — where one AI evaluates another AI's output — you periodically check that the machine's version of quality hasn't drifted from human reality. Automated judges are efficient but they can develop blind spots.


## Slide 13 — Breakout Group Exercise: Plan Your Eval Stack for Juno

Final group exercise of the course. You're building the trust architecture for Juno.

Start with User Feedback — define two mechanisms (one active like a thumbs-up button, one passive like regeneration rate tracking) to monitor Juno's performance in real time.

Move to Human Evaluations — develop 3 rubric questions a Senior PM would use to grade Juno's output. Make them specific and scorable.

Finish with Automated Assessment — identify one binary metric you'd automate via script or LLM-as-a-Judge. Something like "Does the output contain at least one source citation? Yes/No."

Add your Eval Stack Plan into your final project deliverables deck. You've got 25 minutes.


## Slide 14 — AI Levers for Output Optimization

Section three. Your evals told you something isn't working. Now what? You've got three levers to pull.


## Slide 15 — Operationalizing and Measuring AI Risks

Before we talk about optimization, let's set up your dashboard. Four signals to monitor in production:

Blocked Request Rate — how often do safety filters trigger? Example: if 15% of finance queries are blocked, your guardrails might be too sensitive and hurting the UX. Measurement: Total Denied Prompts / Total User Inputs.

Hallucination Rate — what percentage of responses contain factually incorrect claims? Example: a medical bot's error rate rising above 1% triggers an immediate rollback. Measurement: Total Hallucinations / Total Responses.

Human Override Rate — how often does a human correct the AI before the user sees the output? Example: if experts rewrite 40% of AI drafts, the model isn't saving time yet. Measurement: Total Human Edits / Total AI Outputs.

Model Drift & Latency — is performance degrading over time? Example: a model becoming 10% less accurate after a vendor updates the underlying LLM. Measurement: Change in Accuracy + P99 Latency.

These aren't vanity metrics. They're the vital signs of your AI product. If any of them go red, you need to act.


## Slide 16 — The Governance Framework

Four governance strategies that turn metrics into action:

Hard vs. Soft Gates — determine which failures must automatically block a release (a safety failure = auto-block) versus those that need a manual PM sign-off (high latency = PM justifies the release). Not all failures warrant the same response.

Zero-Tolerance Metrics — for hard gates, set specific numerical thresholds. "We require 0% PII leakage." "Hallucination rate must stay below 2%." These are non-negotiable launch criteria.

Grounding for Trust — define output requirements that provide users with evidence. "The model must provide direct citations or links to the policy it referenced." This is your Module 3 RAG requirements meeting your Module 6 eval requirements.

Build a Failure Taxonomy — categorize potential failures into a severity vs. frequency map. Hallucinations in financial data? High severity, fix immediately. Slightly off-brand tone in a greeting? Low severity, fix later. This alignment prevents your team from chasing the wrong problems.


## Slide 17 — Three Levers to Optimize AI Performance

When evals surface a problem, pull the right lever:

The Prompt (Behavior & Logic) — adjust instructions or formatting to influence output. Try few-shot examples, chain-of-thought prompting, or adding delimiters. This is the fastest, cheapest fix. If the problem is behavioral — the model is doing the wrong thing — start here.

The Model (Intelligence & Cost) — swap models or versions to find the best balance of quality, speed, and price. Try comparing Gemini Pro vs. Flash for different task types, or adjust hyperparameters. If the problem is capability — the model can't do the thing — swap the model.

The Data (Knowledge & Accuracy) — refine the information the AI accesses. Clean the RAG dataset, add more diverse data points, or fine-tune. If the problem is knowledge — the model doesn't know the right things — fix the data.

Diagnose first, then prescribe. "The AI is broken" isn't a diagnosis. "The AI hallucinates when asked about Q4 pricing because the RAG knowledge base hasn't been updated since Q3" — that's a diagnosis, and the fix is obvious: update the data.


## Slide 18 — The PM Execution Plan

Four steps to go from eval results to action:

Step 1 — Build Your Eval Plan. Define what to measure, how often, and assign a clear quality owner for the final score. Decision: Speed vs. Certainty. More frequent evals give you faster signal but cost more.

Step 2 — Set Your Gatekeepers. Compare systematic results against your gold standard. Reject any launch based on a "good demo" if the data fails the bar. Decision: Brand Protection vs. Hype. This is where you hold the line.

Step 3 — Add Production Guardrails. Determine when the system must block a response, degrade to a safe script, or escalate to a human. Decision: Safety vs. Utility. Too many guardrails and the product is useless. Too few and it's dangerous.

Step 4 — Evolve Your Roadmap. Use performance gaps to decide whether to pivot your strategy or update your roadmap with new goals. Decision: Feature vs. Data. Sometimes the best thing you can do isn't build a new feature — it's fix the data.


## Slide 19 — Breakout Group Exercise: Finalize Your Project Deliverables

Time to bring it all together. Get into your groups and finalize your project deliverables deck. Here's what each key slide should contain:

Slide 5: Your final System Message with few-shot examples. Slide 6: AI Strategy One-Pager overview and link. Slide 7: RAG Architecture and Data Strategy. Slide 8: 1-2 high-fidelity UX screenshots from Lovable. Slide 9: Agentic Workflow Spec overview and link. Slide 10: Eval Stack plan with rubric questions and hard gate thresholds. Slide 11: Group insights — biggest friction points and "aha" moments.

Feel free to adapt and customize the template. It's a baseline, not a straitjacket. Every team member needs to submit their own copy, but you can build from a shared deck and download separately. You've got 20 minutes.


## Slide 20 — Learner Journey Recap

Let's look at the complete arc of what you've built across six modules:

Module 1 — The Mindset Shift. Moving from deterministic rules to governing probabilistic systems. Your win: mastering prompt anatomy to build reliable system logic.

Module 2 — The Strategic Lens. Moving from shiny distractions to boring killer features. Your win: writing the AI Strategy One-Pager to bridge feasibility and impact.

Module 3 — The Context Shift. Moving from stateless prompts to context-aware RAG systems. Your win: defining an AI PRD with precise retrieval requirements.

Module 4 — The Interface Evolution. Moving from static menus to invisible UIs driven by intent. Your win: architecting the Iceberg flow with trust and transparency.

Module 5 — The Autonomy Dial. Moving from reactive to autonomous agentic systems. Your win: developing the AWSpec for resilient, goal-driven agents.

Module 6 — The Validation Shift. Replacing vibe checks with systematic evaluation. Your win: engineering a multi-layered eval stack with hard gate thresholds.

You now have a complete toolkit for AI product management — from idea to strategy to architecture to experience to deployment to measurement. That's the full lifecycle.


## Slide 21 — Break

Five-minute break before the final showcase. Last break of the course — savor it.


## Slide 22 — Cameras On

Welcome back! Cameras on. Let's see those faces for the grand finale.


## Slide 23 — Final Project Showcase: Demo Your Juno Copilot

This is it — the moment you've been building toward. Volunteer groups get to present their Juno copilot, share their strategic decisions, and get live feedback.


## Slide 24 — LMS Submission Reminder

Important: to qualify for certification, make sure you upload and submit your own copy of the final project deliverables in the LMS. Every team member submits individually. Don't forget this step.


## Slide 25 — Project Deliverables Checklist

Quick recap of what must be in your deck: Core System Prompt, AI Strategy One-Pager & AWSpec overviews, RAG Architecture & Data Strategy overview, UX Design screenshots from Lovable, Eval Stack Plan outline, and Group Insights from the build process.

You don't need to cover every detail of every slide. The goal is demonstrating your strategic thinking, not creating a 50-page document.


## Slide 26 — Key Takeaways

Let me bring it home with a story about Tesla Autopilot.

When Tesla first shipped Autopilot, the demos were magical — the car drives itself, changes lanes, takes exits. But demos don't drive 2 billion miles across every road condition. In production, edge cases appeared that no demo covered — a white truck against a bright sky, faded lane markings in construction zones, a cyclist making an unexpected turn. The demos said "95% accurate." The real world said "that 5% can be fatal." That's takeaway one — vibe checks prove nothing about reliability at scale. You need systematic evaluation that tests the thousand intents your demo never imagined.

Tesla's response was governance with hard lines. Confidence drops below a threshold? The driver is forced to take control — that's a hard gate. A slightly delayed lane-change suggestion? Logged and reviewed but doesn't stop the system — that's a soft gate. The system must never accelerate toward a detected pedestrian — that's a zero-tolerance metric. And a failure taxonomy ensures the team fixes high-severity problems first, not whichever failure got the most press. That's takeaway two — define your hard gates, zero-tolerance metrics, and failure taxonomy before you ship.

Tesla doesn't rely on one type of testing. Automated simulations run millions of virtual miles — that's the automated layer. Safety reviewers grade real-world footage against a rubric — that's the human layer. Every Tesla on the road sends back data on how often drivers disengage or override — that's the user feedback layer. No single layer catches everything. Together, they form a complete safety net. That's takeaway three — build a three-layer eval stack. Automated for speed, human for nuance, user feedback for reality.

And when evals surface a problem — say, the car struggles with lane markings in rain — Tesla diagnoses before prescribing. Is it the instructions? The model? The training data? Each diagnosis points to a different lever. Pull the wrong one and you waste months. Pull the right one and it's fixed in the next update. That's takeaway four — diagnose the root cause, then pull the right lever.


## Slide 27 — Resources and Templates

Here are your final resources — the AI Evals Stack template, the Human Evaluation Rubric template, and the Final Project Rubric Guide. These are tools you'll use well beyond this course.


## Slide 29 — Q&A

Last Q&A of the course. Any questions about evals, guardrails, the optimization levers, the governance framework — or anything from the past six modules? This is your chance. Unmute, chat, or Slack. Let's hear it.

And with that — I want to take a moment before we wrap.

Six modules. Six weeks. You showed up every single time — cameras on, engaged, asking hard questions, challenging each other in breakouts, building something real. That matters more than any certificate.

Think about where you were in Module 1. Most of you had never written a system prompt. Some of you weren't sure what RAG stood for. A few of you told me you were nervous about being "too non-technical" for this. Look at what you built. You wrote AI strategies. You architected RAG pipelines. You designed invisible UIs. You spec'd autonomous agents. You built eval frameworks that would hold up in a real product review. You didn't just learn this stuff — you did it.

Here's what I want you to remember: the AI landscape will keep changing. The models will get better. The tools will get easier. New patterns will emerge. But the fundamentals you learned here — how to think about AI as a product problem, how to validate before you build, how to earn user trust, how to measure what matters — those don't expire. That's your edge.

You came in as product managers. You're leaving as AI product managers. And honestly? Some of the work I've seen from your groups would hold up against teams I've seen at top tech companies. I mean that.

Stay connected. Keep building. Help each other. And when you ship your first AI feature in the real world — send me a message. I want to hear about it.

It's been an absolute privilege. Thank you.
