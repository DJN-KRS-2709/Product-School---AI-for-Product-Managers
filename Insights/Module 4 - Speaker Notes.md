# Module 4: Design AI-Native User Experiences — Speaker Notes

Casual talking points for each slide. Not a script — just the key things to say and the energy to bring. Real examples from companies like Perplexity, Notion, MidJourney, and Google to ground every concept.

---

## Slide 1 — Title

Welcome to Module 4 — Design AI-Native User Experiences. You've got the strategy, the prompting skills, and the RAG architecture. Now we make it feel like magic for the user. This is where product craft meets AI engineering.


## Slide 2 — Class Expectations

Same rules as always. Cameras on, be on time, engage actively, connect with your peers, Slack for everything, deep questions after class. We're past the halfway point now — let's keep the energy high.


## Slide 3 — Syllabus

Quick recap of the journey. Module 1 was mindset and prompting. Module 2 was strategy and validation. Module 3 was RAG and AI PRDs. Now in Module 4, we're designing the experience layer — how users actually interact with all that intelligence you've been building underneath.

This is where a lot of AI products succeed or fail. The AI can be brilliant under the hood, but if the interface is clunky, confusing, or untrustworthy, users bounce. And the reverse is also true — a well-designed AI experience makes users feel like they have a superpower.


## Slide 4 — Agenda

Four sections today. First, intent-driven AI design systems — how AI changes the fundamental relationship between user and interface. Second, designing invisible UI for AI-native outcomes — making the labor disappear, not the AI. Third, how to architect an AI user flow — the "Iceberg" model where the best interfaces hide the complexity underwater. And fourth, the PM's playbook for closing AI trust gaps — because trust is everything.

One note: there's an optional hands-on lab at the end for post-class practice. We'll cover it briefly but the deep work happens on your own time.


## Slide 5 — Intent-Driven AI Design Systems

Section one. We're rethinking what UI means when AI is the engine. Traditional interfaces are like menus at a restaurant — you scan, you pick, you order. AI-native interfaces are like having a chef who already knows what you want.


## Slide 6 — Instructor-Led Q&A: Your Experience With "Clunky" AI-UX

Let's start with your lived experience. Three questions:

What's a product you've tried where AI technically works, but the experience feels wrong, annoying, or pointless? We've all had that moment where an AI feature pops up and you think "why is this here?"

On the flip side — where have you seen AI change how you interact with a product, not just what it can do? Did it remove steps? Did it change who's "in control"? Did it make the product feel proactive?

Feel free to unmute or drop your thoughts in chat. These are the friction points and the "aha" moments that define great AI-UX.


## Slide 7 — Traditional AI-UX vs. AI-Native UX

There's a fundamental distinction here that matters for how you build:

Traditional AI-UX takes existing products and layers AI on top. It's user-driven — the user manually triggers AI actions within a static interface. Think Microsoft Bing adding AI-powered answers to their existing search engine. It enhances what's already there without disrupting familiar habits. Totally valid approach, especially for established products with loyal users.

AI-Native UX puts AI at the product core, built from the ground up. The model is the engine of the workflow. Interactions are intent-driven — the interface evolves in real time to surface only the tools the AI predicts you need. Think Perplexity — an AI-first search engine where responses are generated directly by AI, offering context-aware results with citations. The user never sees a list of blue links.

Neither approach is universally "better." But AI-native products create a more seamless experience when you have the freedom to build from scratch. When you're adding AI to a legacy product, traditional AI-UX is often the right call.


## Slide 8 — Why AI-Native UX Matters

Four reasons this shift in design philosophy matters:

Lowered Interaction Costs — you move the user from manual "searching" to "reviewing and deciding." Instead of navigating five menus to find a report, the AI surfaces it automatically based on context.

Shifted Cognitive Load — you replace repetitive work with automated synthesis. The user focuses on high-level judgment instead of data wrangling. GitHub Copilot doesn't just save keystrokes — it frees up the developer's brain for architecture decisions.

Contextual Relevance — the interface adapts to unique user intents in real time instead of showing the same static menu to everyone. Spotify's Discover Weekly doesn't show you the same playlist as everyone else. It reads your behavior and responds.

Increased System Resilience — by surfacing only the most relevant information exactly when it's needed, you minimize noise and reduce errors. Less clutter means fewer wrong clicks.


## Slide 9 — Designing Invisible UI for AI-Native Outcomes

Section two. "Invisible" doesn't mean the AI disappears. It means the labor disappears. The user should feel like the product just knows what to do next.


## Slide 10 — Invisible by Design

Three principles for designing AI features that feel effortless:

Use environmental signals to trigger actions — the AI starts working automatically when a file is uploaded, a meeting ends, or a form is submitted. No prompt needed. The user doesn't have to ask "please summarize this meeting." It just happens when the recording stops.

Leverage intent prediction to surface micro-UIs — keep the workspace clean by hiding advanced tools until the system predicts the user needs them. In Notion, the AI editing tools don't clutter the page. They appear when you highlight text. The right tool at the right moment.

Automate data flow between workflows — push AI outputs directly into the next stage. If the AI summarizes a support ticket, that summary should flow directly into the CRM record. No copy-paste. No context switching.

The goal isn't to impress users with visible AI features. It's to make them think "this product just works." The best AI is the AI you forget is there.


## Slide 11 — Choosing the AI Interaction Placement

Once you've defined the behavioral logic, you need to decide where in the UI it lives. Three options:

Inline & Embedded — place AI capabilities directly within the text, code, or data rows. This keeps the user in flow. They can transform content without moving their eyes or cursor to a separate menu. Think Google Docs' smart compose — suggestions appear right where you're typing.

Floating & Contextual — use dynamic toolbars or hover menus that follow the user's selection. Advanced editing tools appear only when an object is actively being refined. Notion's AI commands work this way — select text, and a floating menu offers "summarize," "translate," or "rewrite."

Full-Page Canvas & Hubs — dedicate entire views for high-complexity AI outputs like roadmaps, dashboards, or analysis reports. This gives the user space to review, approve, or reject large-scale drafts. Think of a dedicated "AI Analysis" page that shows the full reasoning.


## Slide 12 — Instructor-Led Q&A: Spot the Friction

Let's make this tangible. Here's a scenario: A recruiter opens a candidate's profile. A sidecar chatbox pops up and says: "I have analyzed this profile. Ask me anything or tell me to write an outreach email."

Why is this not an AI-native "invisible" design? What would you change?

Take a minute to think about it. The friction is that the AI is waiting for the user to prompt it. In an AI-native design, the system should have already predicted the recruiter's intent — they opened a profile, so they probably want to send an outreach email. The draft should already be there, ready to review. The chat box makes the user do work that the AI could have done proactively.

What other improvements come to mind? Let's discuss.


## Slide 13 — Mapping Value to UX Treatment

Here's a practical cheat sheet for matching your AI value proposition (from Module 2) to the right UX treatment:

If your value is Automation — use a Full-Page Canvas. Skip the manual work by showing a finished draft in a dedicated space before the user even asks. Think of an AI-generated meeting summary that appears in its own view the moment the call ends.

If your value is Augmentation — use Inline & Embedded. Speed things up by giving the user a starting point right where their cursor is. GitHub Copilot's code suggestions appearing inline are the gold standard here.

If your value is Insights — use Floating & Contextual. Pop up a helpful "aha" moment only when the user selects something. Highlight a data anomaly with an explanation that appears on hover. Tableau's Explain Data nails this — click any data point in a visualization and a floating panel appears, using AI to rank the contributing factors behind that value by statistical significance. It's a contextual "aha" moment exactly when the user is curious.

If your value is Personalization — use Floating & Contextual as well. Change the interface to show only the tools the AI thinks the user needs right now. The UI adapts to the user, not the other way around. Adobe Photoshop's contextual task bar is a great example — when you select an object, a floating toolbar appears with only the actions relevant to what you selected: remove background, generative fill, adjust colors. The tools that surface change based on what the AI predicts you're trying to do next.


## Slide 14 — How to Architect an AI User Flow

Section three. This is the meat of today's module. You're going to learn to think about AI user flows as icebergs — what the user sees is the tip, and the real work happens underwater.


## Slide 15 — Architecting the AI "Iceberg"

Traditional user flow mapping focuses on user clicks, screen navigation, and manual inputs. You draw boxes and arrows showing what the user does at each step.

AI-native mapping is fundamentally different. You're mapping what the system thinks between a user's intent and the final output. Most of the processing is invisible — the model retrieves data, reasons, and generates an output in the background.

As a PM, you must decide what stays "underwater" to keep the experience effortless, and what surfaces as visible UI to build trust. Too much visible? The interface feels cluttered and manual. Too much invisible? The user doesn't trust the output because they can't see how it got there.

This is the art of AI-UX design. Don't just map what the user does — map what the system thinks.


## Slide 16 — The Four Architecture Pillars

When mapping your AI user flow, think in four pillars:

The Trigger — what initiates the process? An environmental signal: a meeting recording ends, a user uploads a PDF, a file changes. The system starts a background task without waiting for a manual prompt. The user sees something like "AI summary in progress..." — a notification, not a request.

The Processing State — the model retrieves data, reasons, and drafts an output. Example: RAG pulls company policy to answer a vacation query. The user sees dynamic breadcrumbs: "Scanning policy docs..." These breadcrumbs build trust by showing progress.

The Presentation — the system selects the best UX treatment based on the value goal. Should this be inline text? A floating suggestion? A full-page canvas? The result deploys via the chosen placement. Example: An inline "V1 Outreach Email" appears directly in the text editor.

The Feedback Loop — the system logs every user edit or "undo" as a signal. If the user clicks "Don't use this tone again," that becomes a preference. Over time, the model improves. This is how the product gets smarter without the user explicitly training it.

Each pillar has both an "underwater" logic layer and a "surface" experience layer. Your job is to design both.


## Slide 17 — How to Map an AI User Flow

Here's the step-by-step you'll use in your group exercise:

Step 1 — Identify the Signal. Capture the specific event or entry point that kicks off the background flow. What triggers the AI? A file upload? A meeting end? A data change?

Step 2 — Map the Hidden Logic. Define the major steps the AI takes before the user sees anything. Which data does it retrieve? How does it reason? What model is it using?

Step 3 — Design the Interaction. Match the sub-steps of the interaction to the correct UI placement (inline, floating, or canvas). What does the user actually see and interact with?

Step 4 — Build the Kill Switch. Map the data flow and generated output to ensure a recovery path exists. The user must always be able to undo, edit, or override.

Use the template linked on the slide. It has specific symbols for each element: signal circles, logic rectangles, interaction squares, and data flow arrows.


## Slide 18 — Example: HR Agent

Let me walk through a concrete example — an HR Agent.

The user enters the HR Agent interface. There's a router that determines: is this a question (Path A) or a task (Path B)?

Path A: User asks "What's the vacation policy?" The system routes to RAG. It retrieves from the HR policy knowledge base. The AI generates an answer with a link to the source policy. The user sees a grounded answer with citations.

Path B: User asks "I want to enter vacation time." The system routes to Tools. It makes an API call to the HR backend (Workday). The AI-driven update processes the request. The user sees a confirmation with a link to their new request on Workday.

Notice: the user sees one simple interface. Underneath, two completely different technical paths are executing. That's the Iceberg in action. The top lane is the only part the user touches. Everything else is underwater.


## Slide 19 — Break

Five-minute break. You've absorbed a lot of design thinking. Let your brain breathe.


## Slide 20 — Cameras On

Welcome back! Cameras on. We've got the group exercise and the trust playbook ahead — let's finish strong.


## Slide 21 — Breakout Group Exercise: Architect Juno's Core AI User Flow

Back to your groups. You're deconstructing the invisible logic behind Juno's most critical skill: scaling your product judgment.

Map exactly how Juno ingests customer transcripts, cross-references them against the RocketShip Strategy One-Pager underwater, and surfaces a defensible priority score on the dashboard.

Start with the Step 1 table — map your entry points, major steps, sub-steps, and generated output. Then move to the drawing space — place your signal at the surface, your logic underwater, and draw the connections through the middle layer showing how the system routes from input to output.

Once finalized, copy and paste your diagram into your final project deliverables deck on the "UX Design" slide. You've got 30 minutes.


## Slide 22 — The PM's Playbook for Closing AI Trust Gaps

Section four. Everything we've designed so far is meaningless if users don't trust it. Trust is the currency of AI products. Let's talk about the three gaps that kill trust and how you close them.


## Slide 23 — Gap 1: The "Black Box" Gap

Users reject AI insights when they can't see the logic or data sources behind the conclusion. If an AI tells a PM "Cut your marketing budget by 20%," the PM's immediate reaction is "Why? Based on what?"

The solution is explainable UI. Two techniques:

Source Scaffolding — link AI summaries back to their original documents using inline citations or hover-states. Perplexity does this beautifully — every claim has a numbered citation that links directly to the source.

Chain-of-Thought Visibility — reveal the reasoning steps for complex tasks. Show which files were searched, which data rows were extracted, what logic was applied. The user sees "the receipts" and can verify in a single click.


## Slide 24 — Gap 2: The Hallucination Gap

Users lose confidence in the entire product when the AI delivers something factually wrong without warning. One bad hallucination can undo months of trust-building.

The solution is confidence signals. Two techniques:

Visual Metadata — apply subtle UI treatments like light-grey text or dotted underlines for areas where the model's confidence is low. This communicates "I'm less sure about this part" without being intrusive.

Proactive Caveats — surface warnings or alternative suggestions when the model identifies multiple possible interpretations. Gemini for Google Workspace lets users rate suggestions, regenerate new ones, or refine the prompt. It acknowledges uncertainty instead of pretending to be omniscient.

The key insight: since AI is probabilistic, it will eventually be wrong. Your job is to design the UI so it doesn't lie to the user when that happens.


## Slide 25 — Gap 3: The Control Gap

Here's the paradox — the more invisible your AI becomes, the more frustrating it is when it gets something wrong. If the user can't easily override, edit, or undo, they feel trapped by the machine.

The solution is kill switches. Two techniques:

One-Click Reversion — provide an immediate "undo" or "restore original" option for any AI-transformed content. The cost of a mistake must be zero. If a user knows they can always go back, they'll trust the AI to try things.

Direct-Edit Access — never present AI output as read-only. Every draft, every suggestion, every automated insight must be instantly editable without requiring a new prompt. MidJourney gets this right — you can select a specific part of an AI image and regenerate just that section instead of starting over.


## Slide 26 — The AI-UX Readiness Checklist

Before you go for "magical invisible UI," make sure you pass the fundamentals. Think of this as a hierarchy of needs:

Level 1 — Functional Baseline. Does the AI trigger reliably at the correct moment? Define strict confidence thresholds so the AI only automates when it's 90% certain of the user's intent. If this breaks, nothing else matters.

Level 2 — Reliability & Verification. Can the user verify the output in under three seconds? Design source scaffolding — citations, logic summaries — to bridge the trust gap without cluttering the UI.

Level 3 — Magical Flow. Does the interaction remove more labor than it creates? This is the ultimate test. Measure the correction rate — if users are constantly fixing the AI's work, revert from invisible UI to a validator UI. Magic that creates work isn't magic at all.

Don't try to build Level 3 before you've nailed Level 1.


## Slide 27 — Managing the Intelligence Tax

Unlike traditional software, AI products come with inherent taxes — properties of working with LLMs that you have to manage through the UI.

The Latency Tax — inference takes time. There's a "dead zone" where the user thinks the app is broken. Solution: streaming text responses and status breadcrumbs. "Scanning backlog..." "Analyzing 47 transcripts..." Turn idle waiting time into active progress.

The Privacy Tax — users are hesitant to share proprietary data with a model they don't own. Solution: permission-first architecture with clear privacy badges. Implement opt-in memory features that give users surgical control over what the AI remembers. "This conversation won't be stored" badges can dramatically increase trust.


## Slide 28 — Quick Debrief: Juno's AI-UX Readiness Statement

Head to Slack. In one sentence: which Level (L2 or L3) are you aiming for with Juno, and what specific UX maneuver or trigger would you add to get there?

This forces you to be specific. "Make it better" isn't a plan. "Add source scaffolding with inline citations so users can verify priorities in under three seconds" — that's a plan.


## Slide 29 — Key Takeaways

Let me bring it home with a story about Google Photos.

Think about the last time you searched your photos. You didn't scroll through 10,000 images. You typed "beach sunset" or "birthday cake" or "dog in the park" — and Google Photos found exactly what you were looking for. No tags. No folders. No manual organizing. The AI just understood what was in your photos and made them searchable. You probably don't even think of Google Photos as an "AI product." It just feels like a really good photo app. That's the highest compliment an AI-native experience can receive. That's takeaway one — the best AI products don't layer intelligence on top of old workflows. They redesign the workflow entirely. Google didn't add an "AI Search" button to a traditional photo gallery. They replaced the entire navigation model with intent.

Now think about what's happening underwater. When you take a photo, Google's system automatically detects faces, objects, locations, and scenes in the background. No prompt. No button press. The environmental signal — a new photo appearing in your library — triggers classification, tagging, and indexing invisibly. When you later type "beach," the system already did the work months ago. That's takeaway two — invisible UI is powered by environmental triggers that automate background tasks. The user becomes a manager of outcomes, not an operator of tools.

But Google also learned trust lessons the hard way. In 2015, Google Photos' image recognition tagged Black people as "gorillas." The backlash was immediate and severe. The AI worked — it classified images — but the failure mode was catastrophic and the product had no safeguards to catch it. Google's response included adding human review layers, confidence thresholds that prevent the system from making low-confidence classifications, and the ability for users to correct and remove tags. That's takeaway three — explainable UI and trust safeguards aren't optional. Source scaffolding, confidence signals, and the ability to correct the AI close the trust gap between "this is cool" and "I depend on this."

And underneath it all, Google Photos is a perfect Iceberg. The user sees a simple search bar and a clean grid of photos. Below the surface: computer vision models, embedding databases, face clustering algorithms, location metadata parsing, and content safety classifiers — all orchestrated invisibly. But at every point, the user can edit, delete, correct, or override. The kill switch is always within reach. That's takeaway four — architect the Iceberg so the hidden logic is powerful but the human always has a recovery path.


## Slide 30 — Extra Practice and Next Session

Two optional exercises:

First — audit a high-friction workflow in your current product for "invisible" UI opportunities. Which steps could move underwater? What environmental signals would trigger the AI?

Second — pick an existing AI feature with low adoption and design an explainable UI that lets users verify outputs in under three seconds.

Next session is Module 5: Deploy Agentic Systems and Workflows. You'll move from single prompts to autonomous agents — multi-step systems that interpret intent, make decisions, and execute tasks. You'll write your Agent Workflow Spec and learn to manage the autonomy dial at a whole new level.


## Slide 31 — Resources and Templates

Here's the AI User Flow Template and the Module 4 Exercise Guide. The flow template is especially useful — you'll use it for your final project deliverables.


## Slide 32 — Q&A

Open floor. Questions about invisible UI, the Iceberg model, trust gaps, the readiness checklist? Anything from today that needs clarifying? Unmute, chat, or Slack — let's hear it.


## Slide 33 — Optional Post-Class Lab: Reimagine Juno as an AI-Native Copilot

For those who want extra practice, there's an optional hands-on lab where you'll take everything from today and reimagine Juno as a fully AI-native copilot in Lovable. Follow the walkthrough linked on the next slide. This is great practice for your final project.


## Slide 34 — Lab Exercise Outcome Preview

Here's a preview of what you'll build if you do the optional post-class lab. Follow the walkthrough guide to get there. Take your time — this one's about quality, not speed.


## Slide 35 — Thank You

Fantastic session today. You went from thinking about AI as a backend system to designing the experiences that make it feel magical and trustworthy. That's a rare skill. See you next time!
