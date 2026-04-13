# Module 1: Drive AI-First Execution with Prompting — Speaker Notes

Casual talking points for each slide. Not a script — just the key things to say and the energy to bring. Real examples from companies like Google, Spotify, GitHub, and Grammarly to ground every concept.

---

## Slide 1 — Title

Welcome to Module 1 — Drive AI-First Execution with Prompting. This is where the journey begins. Let's go.


## Slide 2 — Class Expectations

Quick housekeeping before we dive in. Cameras on — I know it can feel weird, but it genuinely makes the experience better for everyone. Arrive on time so we don't lose momentum. Engage with each other — you're building a network here, not just sitting in a lecture. Make sure your tools and accounts are already set up — we won't be pausing to troubleshoot logins. Use Slack for all communication so nothing gets lost. And if you've got a deep-dive question that's going to take us on a 20-minute tangent, save it for after class — I promise we'll get to it.


## Slide 3 — Introductions

Alright, let's get to know each other. I'll kick things off — share your background, how you got into product, and a couple of career highlights. Don't be shy about the fun stuff. People remember you for the human details, not the job title.

Then it's your turn. Drop your name, where you're based, your current role, and what you're hoping to get out of this course in the Slack channel. Bonus points for a fun fact — the weirder, the better. And throw your LinkedIn profile in there too. The people in this room are your future collaborators, so start connecting now.


## Slide 4 — Final Project Explanation

Let's talk about where this whole course is headed. I'm going to play a short video that walks you through the final project requirements in detail. Pay attention — this is the thing you'll be building toward across all six modules. Think of it as your north star for the next few weeks.


## Slide 5 — Final Project Deliverables

Here's what you'll actually submit. Seven deliverables: your system message, an AI Strategy One-Pager with a link, your RAG architecture and data strategy, UX design screenshots from Lovable, an agentic workflow spec with a link, your evaluation plan, and group insights.

Don't panic — you won't build all of this today. Each module adds a layer. By the end, these pieces snap together like Lego. The full brief and the presentation template are linked right there on the slide. Bookmark them now. You'll be glad you did.


## Slide 6 — Syllabus

Here's the full roadmap for the course. Six modules, and each one builds on the last.

Module 1 — that's today — is all about the AI-first mindset and getting your hands dirty with prompting. You'll build your first prototype of Juno, your AI copilot.

Module 2 shifts to strategy. You'll learn to validate whether an AI bet is actually worth pursuing, and you'll write your AI Strategy One-Pager. Think of it like this: just because you can build something with AI doesn't mean you should.

Module 3 goes deep on RAG architecture — that's how you ground AI in real data instead of letting it hallucinate. You'll define the technical requirements for an AI PRD.

Module 4 is about designing AI-native user experiences. Not just slapping a chatbot on a screen, but rethinking what interfaces look like when AI is the engine.

Module 5 brings in agents. You'll move from single prompts to multi-step autonomous workflows and write your Agent Workflow Spec.

And Module 6 closes the loop — evals, guardrails, and measuring quality. Because "it looks good to me" doesn't scale. You'll replace vibe checks with systematic measurement.


## Slide 7 — Agenda

Here's our game plan for today. Four sections. First, we'll talk about the AI-first product mindset — the mental shift every PM needs to make. Then we'll break down the anatomy of a high-quality prompt — the difference between asking a question and configuring a system. After that, hands-on lab time — you'll build your first Juno prototype in Lovable. And we'll wrap with prompting as product configuration — system messages, techniques, hyperparameters, and how prompts replace PRDs.


## Slide 8 — The AI-First Product Mindset

This kicks off our first big section. The AI-first product mindset isn't about adding AI features to your product. It's about fundamentally rethinking how you build products when AI is at the core. Let's dig in.


## Slide 9 — Instructor-Led Q&A: AI-First Product Thinking

Before I lecture at you, I want to hear from you. Two questions to chew on:

First — in an AI-first product, what user signals matter more than a rigid list of feature requirements? Think about intent, behavior, patterns. The stuff that's hard to put in a Jira ticket.

Second — if you could stop writing every single "if/then" rule for your engineers, what would you stop doing as a PM so you could focus on higher-level strategy?

Feel free to unmute or drop your thoughts in the chat. There are no wrong answers here — just perspectives. I'll share my own experience too. I spent years writing detailed specs that tried to account for every edge case. And the honest truth? The edge cases always won.


## Slide 10 — Every PM Is Now an AI PM

Here's the thing — AI isn't a specialty anymore. It's table stakes. Remember when we used to say "Mobile PM"? Nobody says that now because every PM is expected to understand mobile. Same thing is happening with AI.

Whether you're managing infrastructure, UI, or core features, you're now managing outcomes in a probabilistic world. The sooner you internalize that, the faster you'll adapt. You don't need to become a machine learning engineer. But you absolutely need to understand how these systems work, what they're good at, and where they break.


## Slide 11 — From Rules to Probabilities

This is arguably the single biggest mental model shift for a PM in this era. Let me break it down.

Most software you've managed in your career is deterministic. Same input, same output, every single time. You type 2+2 in Excel, you get 4. You enter your password, the login either works or it doesn't. Predictable. Reliable. Boring in the best way.

AI-powered products are probabilistic. The same input can produce different — and equally valid — outputs each time. Ask an LLM to summarize an article twice and you'll get two different summaries. Both might be great. Or one might hallucinate a fact that doesn't exist.

Think about it like a GPS. The old way was turn-by-turn directions — deterministic, rigid, breaks if there's a detour. The AI way is more like Waze — it evaluates traffic, road conditions, and your history, then gives you its best prediction. Usually great. Occasionally sends you through a weird alley. That's the world you're building for now.


## Slide 12 — The PM's Dual Role

So how do you operate in this uncertain world? AI creates a dual role for PMs.

When you're building AI products — scoping requirements, working with engineering — you can't define a single exact output anymore. Your PRD has to evolve. Instead of specifying "the system shall display X," you're specifying the qualities and guardrails of an acceptable response range. You're defining the boundaries of good enough.

When you're using AI in your own workflows — drafting specs, analyzing feedback, creating presentations — the variability is actually a superpower for creativity. But it means you're responsible for critically evaluating every output. The AI gives you a first draft, not a final answer. You're the quality filter.

Grammarly is a perfect example of this dual role in action. The product team doesn't define every possible grammar correction. They define the guardrails — tone, formality level, audience — and the AI figures out the specifics within those boundaries.


## Slide 13 — How the AI-Era PM Role Has Evolved

Four ways your job has fundamentally changed:

First, assess the "AI-ability" of the problem. Not everything needs AI. If a deterministic rule gives you better predictability and value, use that instead. Don't build a machine learning model to do what a simple if-statement handles perfectly.

Second, own the "vibe" and trade-offs. You're now configuring the balance of cost, latency, and quality. These aren't abstract concepts — they're dials you turn. Low temperature for product logic, high temperature for brainstorming. You make those calls.

Third, define the failure state. AI will fail. That's not a bug — it's a property of probabilistic systems. Your job is to design for that failure. What happens when the model hallucinates? What's the fallback? Where does the human step in? Spotify's Discover Weekly occasionally serves up a bizarre recommendation. But the UX handles it gracefully — you just skip the song.

Fourth, prototype as spec. Stop writing 40-page documents that describe what you want. Build it. Show it. Prove the logic works with a functioning prompt, not a paragraph.


## Slide 14 — A PM's AI Toolkit

Quick overview here — this is a directory of AI tools you should be aware of as a PM. I'm not going to walk through every single one. Browse it on your own time, try a few, and find the ones that click for your workflow. The landscape changes fast, so the specific tools matter less than understanding the categories: prototyping, analysis, code generation, design, research.


## Slide 15 — The Anatomy of a High-Quality Prompt

Alright, section two. We're going from mindset to mechanics. If the last section was about how to think, this section is about how to do. Let's talk about what actually makes a prompt work.


## Slide 16 — The Four Dimensions of a Prompt

Ambiguity is the enemy of consistency. If your prompt is vague, the model's output will be unpredictable. To get reliable results, every prompt needs four things:

Role — defines the model's expertise. "Act as a senior B2B product researcher." This isn't just flavor text. It activates different knowledge patterns in the model. A "senior researcher" writes differently than a "junior intern."

Task — defines the specific goal. "Synthesize insights from raw feedback." Be precise. "Help me with feedback" is not a task. It's a wish.

Constraints — defines the guardrails. "Do not speculate. Use only the provided transcript." This is your safety net. Without constraints, the model will happily invent things that sound plausible but are completely made up.

Format — defines the output structure. "Return a markdown table with headers." If you don't tell the model what shape the output should be, you'll get a wall of text when you wanted a table.

Think of it like hiring a contractor. You wouldn't just say "build me something nice." You'd specify the role (architect vs. electrician), the task (design a kitchen), the constraints (budget of $50k, must keep the existing plumbing), and the format (deliver blueprints, not a verbal description).


## Slide 17 — Hands-On Lab: Prompt-to-Prototype Your Copilot with Lovable

Time to build. We're shifting from theory to practice. You're about to create your first functional prototype of Juno — your AI copilot — using Lovable. Let's get our hands dirty.


## Slide 18 — Lab Exercise: Prompt-to-Prototype

Alright, let me walk you through this live. I'm going to build Juno right in front of you, step by step. Follow along with me — we're doing this together.

**Step 1: Create the Juno Baseline in Lovable**

Open Lovable. If you haven't created an account yet, take a minute to do that now. Once you're in, you'll see the prompt box. We're going to use the pre-built Juno baseline prompt to get moving fast. Paste this in and hit enter:

*"Act as a Senior Frontend Engineer. Build a clean, dark-mode Dashboard for 'Juno.' Left Column: Input area for 'Raw User Transcripts.' Middle Column: 'Structured Insights' (Cards with Priority/Sentiment). Right Column: 'Draft PRD' (Markdown preview). Add a 'Process' button that triggers a loading state."*

Watch the magic happen. Lovable will generate a full three-column dashboard in seconds. Dark mode, structured layout, process button — the whole thing. Take a look at what it produced. Not bad for one prompt, right?

Quick note — if Lovable asks you about cloud integration and you're on a free account, click "Decline." You don't need it for this exercise.

**Step 2: Make It Look Like a Real Product with an Asana Screenshot**

Now here's where it gets fun. The dashboard works, but it looks generic. Let's make it look like it belongs in a real product ecosystem. I'm going to use Asana as my design reference.

Take a screenshot of Asana's dashboard — the project view works great. You want to capture the colors, the typography, the spacing, the overall feel. Got it? Good.

Now in Lovable, click the "+" button in the chat area and choose "Attach" or "Take a Screenshot." Upload your Asana screenshot, and then add this prompt alongside it:

*"I am uploading a screenshot of Asana's dashboard. Update Juno's colors, typography, and component styling to match this design system exactly."*

Hit enter. Watch Lovable restyle the entire dashboard to match Asana's aesthetic — the color palette, the clean sans-serif fonts, the card spacing, everything. In one prompt, Juno went from "generic dark mode app" to "this looks like it ships with Asana." That's the power of screenshot-driven design.

You can also use the "Design" button at the top of the preview window to quickly toggle between color themes if you want to experiment further.

**Step 3: Test It with Real Data**

Now let's see if this thing actually works. Copy the user interview artifact from the walkthrough guide — it's the transcript from Sarah, the Data Analyst at RocketShip. She's frustrated about CSV exports crashing, a bright blue nav bar, and wanting dark mode. Real messy, real-world data.

Paste that transcript into the left column — the "Raw User Transcripts" input area. Then hit the "Process Transcript" button.

Watch the loading state trigger. Then look at the middle and right columns. Does Juno parse the transcript into structured insights? Does it identify priority and sentiment? Does it generate a draft PRD?

Here's the important part — where does it fall short? Maybe it missed the severity of the CSV crash. Maybe it over-weighted the dark mode request. Maybe the PRD draft is too vague. Those gaps are exactly what we'll be fixing across the rest of the course. For now, just observe and note what surprised you.

You've got 25 minutes total. I'll be building alongside you in real time. If you prefer a different tool like Google Stitch or Bolt, go for it — the methodology works everywhere. But follow these three steps regardless of which tool you use.


## Slide 19 — Quick Debrief: Your Copilot Prototype Statement

Head to Slack and in one sentence, tell us: when you pasted the artifact and pressed "Process," where did the prototype fall short?

This is a two-minute exercise but it's important. Naming the gap between what you expected and what you got is the entire game of AI product management. Every time you identify where a prototype breaks, you're developing your product instinct for probabilistic systems.


## Slide 20 — Break

Five-minute break. You've earned it. Grab some water, stretch your legs, check your phone. We'll pick right back up.


## Slide 21 — Cameras On

Welcome back! Quick reminder — cameras on. I know it's tempting to go stealth mode after a break, but we're better together when we can actually see each other.


## Slide 22 — Prompting as Product Configuration

Alright, final section of the day. This is where we connect everything. Prompting isn't just a skill — it's your new product configuration tool. Let me show you what I mean.


## Slide 23 — Prompt Layers for Product Configuration

In the lab, you were working in the Middle Layer — writing user prompts. But real AI products have three layers, and understanding all three is what separates a PM who uses AI from a PM who builds AI products.

The Foundational Layer is the system message. Think of it as the AI's constitution — the rules that never change. It sets the persona, boundaries, and safety protocols. Example: "You are a Senior Data Analyst. Output only JSON." This runs silently behind every interaction.

The Middle Layer is the user prompt. This is the dynamic part — whatever the user types or triggers. "Analyze this churn report for insights." It changes with every interaction.

The Top Layer is tools and functions. This is where the model goes beyond text generation. It can call a calculator, search a CRM, hit an API. This is what turns a chatbot into an actual product.

When you built Juno in the lab, Lovable's own system message was doing heavy lifting behind the scenes. You didn't see it, but it was there — constraining and guiding the model's behavior. Now you're going to learn to write those invisible rules yourself.


## Slide 24 — The Prompting Strategy Matrix

Three core techniques you need in your toolkit:

Zero-Shot — you give the AI a task with no examples. Just instructions. Great for brainstorming, generating hypotheses, or drafting interview scripts. When you need volume and speed over precision, zero-shot is your friend. "List 10 potential user problems for a pet sitting app." Quick, broad, gets the ideas flowing.

Few-Shot — you give 2-3 examples to guide the AI's structure or style. This is your secret weapon for consistency. When you need the AI to match your team's exact template — acceptance criteria, JSON schemas, status updates — few-shot locks it in. "Here are 3 examples of our user stories. Write a new one following this exact format."

Chain-of-Thought — you ask the AI to explain its reasoning step by step before answering. This is for complex logic — market sizing, feedback analysis, prioritization decisions. It forces the AI to "show its work," which makes it dramatically less likely to jump to a lazy conclusion. "Think step-by-step. First, estimate the TAM. Then apply our segment filters to calculate the SAM."


## Slide 25 — Few-Shot Prompting in Practice

Let me show you why examples matter. Say you want to classify user feedback as a Feature Request, Bug, or Praise.

Zero-shot version: "Classify this feedback: 'The reports load slowly.'" The model guesses "Bug." Seems reasonable, right? But on your team, "slow" means a performance improvement request — that's a Feature Request, not a Bug.

Few-shot version: You add three examples. "'Login is slow' → Feature Request. 'Login returns 404' → Bug. 'Love the login!' → Praise." Now when the model sees "reports load slowly," it pattern-matches to "Login is slow" and correctly tags it as a Feature Request.

Instructions tell the model what to do. Examples show it how. That's the difference. And here's the nuance — zero-shot isn't "bad." It's excellent for creativity and first drafts. But when you need the output to match a specific standard, few-shot is how you get there.


## Slide 26 — Chain-of-Thought Prompting in Practice

Now, why isn't few-shot enough for everything? Because pattern matching breaks down when you need actual reasoning.

Here's the scenario. "Is 'Add AI Avatars' a high-priority feature? Context: Our Q3 goal is reducing churn." Without chain-of-thought, the model sees "AI" — hot topic — and predicts "High Priority." It's doing pattern matching, not thinking.

With chain-of-thought: "Think step-by-step. First, define the primary driver of churn. Then evaluate if AI Avatars directly solves that driver. Then assign priority based only on that evaluation." Now the model reasons: "Churn is driven by high costs. AI Avatars add value but don't reduce cost. Conclusion: Priority Low."

Same question, totally different — and correct — answer. Few-shot is perfect for style. Chain-of-thought is for logic. You'll use both, often in the same prompt.


## Slide 27 — Breakout Group Exercise: Configure Juno's System Prompt

Time for the big group exercise. You're going to build the foundational layer for Juno's first core skill: Evidence Extraction. This is where you give Juno its "job description."

Here's the play. First, assign roles in your group and skim the five artifacts to separate signal from noise. Then define the Role and Task — Juno is an AI Associate PM that synthesizes raw discovery notes into a structured opportunity brief. Set Constraints and Format — Juno never invents quotes, always cites source IDs, follows a specific output schema. Add a "Golden" few-shot example showing Juno how to filter chaos into a strategic insight. And finally, add a chain-of-thought instruction forcing Juno to surface risks and assumptions step-by-step before generating the final brief.

You've got 30 minutes. The groups you form now will be your groups for the rest of the course — so choose wisely, or at least choose people who make you laugh. Use the exercise guide linked on the slide.


## Slide 28 — Hyperparameters: Model Configuration

We've covered the text of the prompt. Now let's talk about the settings — the operating environment your prompt runs in.

Temperature is the risk slider. Low (around 0.2) for product logic, code, and data where you need precision and consistency. High (0.7+) for ideation, brainstorming, and creative chat. Think of it like a volume knob — turn it up when you want wild ideas, dial it down when you need reliable answers.

Top P is the quality bar. It limits the model to only the top percentage of likely words. This is how you cut off "weird" or "long-tail" hallucinations without making the model boring. It's a scalpel where temperature is a sledgehammer.

Max Tokens is the budget knob. It sets a hard limit on output length, which directly controls latency and cost. Always set this. Without a limit, the model will happily ramble for 10,000 tokens, get stuck in loops, or burn through your API budget while you're at lunch.

Your prompt is the software. These settings are the operating environment. You need both.


## Slide 29 — The Role of Fine-Tuning

You might be thinking: "Wait, if few-shot prompting handles style, why do I need fine-tuning?" Great question. The answer is scale and latency.

Fine-tuning bakes instructions directly into the model's weights. Unlike few-shot prompting, you don't need to send long, expensive examples with every single API call. That reduces latency and cost at scale.

GitHub Copilot is the perfect example. It isn't just "prompted" to write code. It's fine-tuned on billions of lines of code to instinctively understand syntax, style, and logic patterns. It doesn't need instructions each time — the knowledge is baked in.

But here's the critical misconception — don't use fine-tuning to teach the model your proprietary data. Models are probabilistic engines, not databases. They can't "look up" facts. They'll hallucinate anything they're not 100% sure about. For proprietary data, you need RAG — Retrieval-Augmented Generation. That's Module 3. For now, remember: fine-tuning is for behavior and style, not knowledge and facts.


## Slide 30 — The Optimization Decision Framework

As an AI PM, your stakeholders will come to you shouting "The AI is broken!" or "We need to fine-tune immediately!" Your job isn't to say yes. Your job is to diagnose the actual problem and pick the right tool.

Problem 1: "The model gives inconsistent answers." Fix: Few-Shot Prompting. If outputs oscillate between good and bad, the model just needs clearer guardrails and examples. This is the fastest, cheapest fix.

Problem 2: "The model doesn't know our specific data." Fix: RAG. If a user asks about a specific refund status or policy document, no amount of prompting will help. The model needs to actually read your database. We'll go deep on this in Module 3.

Problem 3: "The model sounds like a robot, not our brand." Fix: Fine-Tuning. If the content is correct but the vibe is wrong — too formal, wrong syntax, generic tone — you need to retrain the model's weights to instinctively mimic your voice.

This is your diagnostic framework. Memorize it. You'll use it every week.


## Slide 31 — From PRDs to Prompts

Here's how all of this fits into your actual day-to-day.

The old way: you wrote a paper spec. "The chatbot should be helpful and polite." You handed it to engineering. You waited two weeks. And then you discovered that "polite" means completely different things to you, the engineer, and the model.

The new way: you write a prompt spec. A working system prompt using the four-part anatomy and prompting techniques. You build the logic in a playground and test edge cases immediately. Then you hand engineering a working prompt that proves the logic works. No guessing. No misinterpretation. No two-week wait to discover a misalignment.

This is the biggest practical shift in your workflow. You're no longer describing what you want — you're demonstrating it. And that changes the entire dynamic with your engineering team.


## Slide 32 — Key Takeaways

Let me bring it home with a story you've probably already experienced.

When GitHub launched Copilot, the product team didn't write a 40-page spec that said "generate code suggestions." They configured a system. They defined the role — act as a pair programmer who understands the developer's codebase. They set constraints — don't suggest deprecated APIs, respect the project's language and style. They tuned the format — inline suggestions that appear as ghost text, not a chatbot window. And then they shipped it. But here's the thing — they didn't ship and forget. The first version was rough. It suggested insecure code patterns. It hallucinated function names that didn't exist. So they kept steering. They adjusted the prompting, fine-tuned on better data, and added guardrails. Every week, the product got a little more reliable. That's takeaway one — the product lifecycle has changed. AI features aren't buttons you ship and walk away from. They're living systems that need continuous steering. The good news is that tools like Lovable let you validate in real time instead of waiting for a sprint cycle.

Now, GitHub's team could have just told engineering "make it helpful." Instead, they wrote precise system prompts that configured Copilot's behavior — what context to read, what patterns to follow, what to avoid. That invisible layer of system instructions is what makes Copilot feel smart rather than random. That's takeaway two — system prompting is the new invisible code. The anatomy of Role, Task, Constraints, and Format isn't a hack. It's the standard configuration pattern. Master it and you move from chatting with AI to building real system logic.

And when Copilot's outputs weren't matching developers' expectations, the team didn't just "try harder prompts." They diagnosed the root cause. Style inconsistencies? Few-shot examples of the project's coding conventions. Hallucinated APIs? RAG grounded in the actual repository. Still too generic across languages? Fine-tuning on language-specific corpora. Each problem had a specific solution. That's takeaway three — choosing between Prompting, Few-Shot, RAG, and Fine-Tuning is a strategic diagnosis. The optimization framework you learned today is how you pick the right tool. That's what separates an AI PM from someone who just uses ChatGPT.


## Slide 33 — Extra Practice and Next Session

Two optional exercises if you want to go deeper:

First — go back to your Lovable project and prompt Juno to generate a strategic dashboard view. Use a "Vibe" prompt to style it like a professional analytics tool. See how far you can push the design.

Second — audit a manual task in your current job for "AI-ability." Pick something repetitive and rule-based. Draft a system message using the anatomy framework to automate it. Does it need few-shot examples to match your company's voice, or is zero-shot enough?

Next session is Module 2: Validate AI Opportunities and Technical Feasibility. You've learned how to build with AI. Now the question becomes: are you building the right thing? You'll learn to select and shape AI bets that actually move business metrics, and you'll create your AI Strategy One-Pager.


## Slide 34 — Resources and Templates

Here are all the resources for this module — the final project brief, the deliverables template, and the Module 1 Lab Guide. Bookmark these. You'll reference them throughout the course.


## Slide 35 — Q&A

Alright, we're at the finish line. Any questions about what we covered today? This is your time — unmute, drop it in the chat, or save it for Slack if something comes to you later. No question is too basic or too deep. Let's hear it.


## Slide 36 — Thank You

Great session, everyone. See you next time!
