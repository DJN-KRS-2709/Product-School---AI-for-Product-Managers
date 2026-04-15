# Student Evaluation Methodology

**Course:** AI Product Management — Product School  
**Evaluator:** AI-assisted evaluation (Claude / Cursor Agent)  
**Date:** April 2026  
**Cohort:** Group final projects (Juno — Associate AI PM Copilot)

---

## 1. Evaluation Framework

Each group submitted **final project deliverables** documenting the Juno copilot: system prompt, AI strategy, RAG architecture, UX, agent workflow (AWSpec), evaluation plan, and build insights. Submissions were received as **PDFs** and **PowerPoint decks** (`.pptx`). Some files were duplicate exports, empty scans, or unrelated course templates; those were deduplicated or flagged as unscorable (see §3).

The evaluation rubric was derived from the **course modules** that map to the official deliverables template:

| Module | Deliverable angle |
|--------|-------------------|
| **Module 1** | System message — role, task, constraints, few-shot |
| **Module 2** | AI Strategy One-Pager — problem, metrics, autonomy, scope |
| **Module 3** | RAG & data — sources, retrieval, grounding |
| **Module 4** | UX — iceberg flow, trust signals, interface evidence |
| **Module 5** | AWSpec — actors, pattern, memory, tools |
| **Module 6** | Evaluation plan — definition of “good,” eval stack, mitigations |

### Scoring Scale

- **Maximum:** 100 points  
- **Floor:** **0 points** — incomplete, blank, or unscorable submissions can score at the floor. *(This differs from the Vibe Coding cohort, where a higher floor reflected “everyone shipped a working prototype.” Here, some artifacts are outlines or template-only.)*  
- **Score bands (interpretive):**
  - **90–100:** Exceptional — comprehensive, strategic, documentation-ready  
  - **70–89:** Strong — solid across most dimensions; may have one weaker area  
  - **50–69:** Partial — real substance in places; major gaps or one critical error (e.g., off-brief RAG content)  
  - **Below 50:** Incomplete — placeholders, outline-only, or not assessable  

---

## 2. Evaluation Criteria (7 Dimensions)

| Dimension | Weight | What Was Evaluated |
|-----------|--------|--------------------|
| **System Message** | 15 pts | Role, task, constraints, citation / hallucination rules, few-shot example quality |
| **AI Strategy One-Pager** | 15 pts | Problem & workflow, target metrics, autonomy level (copilot vs agent), risks & mitigations, V1 scope (In/Out), link to Module 2 artifact where present |
| **RAG & Data Strategy** | 15 pts | Data sources, sync / freshness, hybrid retrieval, Top-K, grounded trust & fail-safes |
| **UX & Interface** | 15 pts | Trigger → processing → presentation → feedback; trust UI; screenshots or demo evidence |
| **Agent Workflow (AWSpec)** | 20 pts | Actors, pattern (e.g., ReAct / planner-executor), memory, tools, autonomy consistency, stop conditions |
| **Evaluation Plan** | 10 pts | Definition of “good,” human + automated + user signals, mitigations, hard gates |
| **Insights & polish** | 10 pts | Friction, learnings, aha moments; completeness and coherence across the deck |

### Why AWSpec is weighted highest (20 pts)

The capstone rewards **systems thinking**: how Juno executes end-to-end (who does what, what can go wrong, what stops the chain). That is the hardest and most transferrable PM skill for AI products—parallel to **Engineering Handoff** in the Vibe Coding rubric.

---

## 3. Evaluation Process

### Step 1: Establish Context

Read the **Module 1–6 speaker notes** (and the final deliverables checklist) so scoring aligns with what was taught, not generic “AI slop” standards.

### Step 2: Ingest Submissions

- **PDF** — text extracted with `pypdf` (Python). Some PDFs are image-only or corrupt; those are marked unscorable until re-uploaded.  
- **PPTX** — text extracted with `python-pptx` (slide shapes). Alternative: unzip `.pptx` and parse `ppt/slides/slide*.xml` (same approach as the Vibe Coding methodology).  

```python
# Example: extract text from .pptx with python-pptx
from pptx import Presentation
prs = Presentation("deck.pptx")
for slide in prs.slides:
    for shape in slide.shapes:
        if hasattr(shape, "text") and shape.text:
            print(shape.text)
```

### Step 3: Deduplicate and Scope

- Treat **duplicate exports** (same team, same content) as **one** submission.  
- Treat **unrelated templates** (e.g., a different final presentation brief) as **out of scope** for the Juno rubric unless the instructor requests a separate assessment.  
- **Empty or blank PDFs** — score **0** until a readable file is provided.

### Step 4: Score Each Submission

Each artifact was scored independently across all **7** dimensions. Scoring was based on:

- **Presence:** Is the section present and on-brief (not pasted from another domain)?  
- **Depth:** Specificity — APIs, thresholds, examples vs. generic bullets.  
- **Quality:** Evidence of understanding (e.g., copilot vs agent alignment, eval stack vs “we’ll test it”).  
- **Originality:** Own framing in insights; not only template placeholders.

### Step 5: Rank and Calibrate

- Rank **groups** by total score.  
- Check that similar depth → similar totals; flag outliers (e.g., strong insights but catastrophic RAG paste).  
- Confirm that **incomplete** work is not inflated to “passing” solely because the cohort is small.

### Step 6: Write Personalized Feedback

Each ranked entry received **personalized feedback** in the interactive scorecard (warm tone, concrete references, **standout** or **next step** callouts)—same spirit as the Vibe Coding scorecard, adjusted for team submissions.

---

## 4. Scoring Rubric Detail (Summary)

### System Message (15 pts)

| Band | Criteria |
|------|----------|
| 14–15 | Full role/task/constraints; explicit “never invent”; strong few-shot with evidence IDs and assumptions labeled |
| 11–13 | Most elements present; few-shot lighter or constraints thinner |
| 6–10 | Generic prompt; missing few-shot or weak guardrails |

### AI Strategy One-Pager (15 pts)

| Band | Criteria |
|------|----------|
| 14–15 | Clear bet, metrics, autonomy choice justified, V1 In/Out, risks; link to artifact where required |
| 11–13 | Solid strategy; metrics or scope less crisp |
| 6–10 | High-level only; missing autonomy or scope boundaries |

### RAG & Data Strategy (15 pts)

| Band | Criteria |
|------|----------|
| 14–15 | Named sources, retrieval strategy, Top-K, grounding / insufficient-evidence path |
| 11–13 | Sources + strategy sketched; less operational detail |
| 0–10 | Missing, generic, or **off-brief pasted content** (major deduction) |

### UX & Interface (15 pts)

| Band | Criteria |
|------|----------|
| 14–15 | Iceberg / pillars mapped; trust behaviors; **screenshots or clear demo proof** |
| 11–13 | Good narrative; limited UI evidence |
| 6–10 | Placeholders; “link later” with no proof |

### AWSpec (20 pts)

| Band | Criteria |
|------|----------|
| 17–20 | Actors, pattern, memory, tools, permissions; fail-safes; autonomy consistent with copilot story |
| 13–16 | Solid workflow; naming or autonomy inconsistencies |
| 0–12 | Missing, vague, or contradictory autonomy levels |

### Evaluation Plan (10 pts)

| Band | Criteria |
|------|----------|
| 9–10 | Definition of good + layered eval (human / auto / user) + mitigations / gates |
| 7–8 | Partial stack; lighter methodology |
| 0–6 | Boilerplate or missing |

### Insights & polish (10 pts)

| Band | Criteria |
|------|----------|
| 9–10 | Specific friction and aha; reflection shows meta-learning |
| 7–8 | Present but thinner |
| 0–6 | Missing or only template text |

---

## 5. Output

The evaluation is delivered as an interactive HTML scorecard (`evaluation-scorecard.html`):

- **Summary statistics** — teams counted, average, highest, lowest  
- **Evaluation criteria** — 7 dimensions with point weights  
- **Top 3 podium** — highest-scoring groups  
- **Full rankings** — expandable cards with per-dimension breakdown and personalized feedback  

Publish via **GitHub Pages** (or any static host) for sharing—same pattern as the Vibe Coding course:

**Interactive scorecard (results):** [`evaluation-scorecard.html`](evaluation-scorecard.html)

---

## 6. Final Rankings (this run)

| Rank | Team / artifact | Score |
|------|-----------------|------:|
| 1 | Dimi Kurtti, Olivia Anastassov, Celia Trifoi, Morgan Collins, Abdulmohsen Alfaraj — *Building Juno* | 97 |
| 2 | Team 2 PMC 5758 (Jessica, Katinka, Matt, Mosaab, Sonia, Valeria) | 93 |
| 3 | Alex Kroller, Jared Lewis, Michael Neuschwander, Nakedi, Salma K | 66 |
| 4 | Unattributed Juno template (placeholders) | 40 |
| 5 | Berenice Pernalete, Julie Nelson, Rasana Anandan — outline deck | 20 |
| 6 | Blank / unscorable PDF | 0 |

**Average score (all six rows):** 52.7 / 100  

**Average excluding unscorable (0):** 63.2 / 100  

---

## 7. Key Observations

- **Strongest dimension overall:** **Evaluation plan** among teams that finished — several submissions explicitly mirrored the three-layer eval stack (Modules 6).  
- **Most variable dimension:** **UX evidence** — ranged from rich iceberg narrative to placeholders with no screenshots.  
- **Highest-risk failure mode:** **Wrong-domain content** in RAG or data slides (copy-paste from another project) — breaks trust for the whole submission until fixed.  
- **AWSpec quality:** Top teams separated on **ReAct / multi-agent clarity**, memory + tool boundaries, and stop conditions.  
- **Incomplete submissions:** Outline-only decks score low by design; the methodology does **not** apply a participation floor.

---

*Interactive scorecard: [evaluation-scorecard.html](evaluation-scorecard.html)*  
*Reference (parallel course): [AI Vibe Coding — METHODOLOGY](https://github.com/DJN-KRS-2709/AI-Vibe-Coding---Product-School/blob/main/Student%20Evaluation/METHODOLOGY.md) · [Interactive scorecard](https://djn-krs-2709.github.io/AI-Vibe-Coding---Product-School/Student%20Evaluation/evaluation-scorecard.html)*
