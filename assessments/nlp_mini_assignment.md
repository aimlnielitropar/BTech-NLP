# Mini-Assignment: Multilingual Customer-Support Ticket Triage System
### B.Tech NLP, Semester V — Capstone-style Mini-Assignment

## Title
**Building an End-to-End Ticket Understanding Pipeline for an E-Commerce Support Desk**

## Industry Context (share this with students)
Every major e-commerce and SaaS company (Flipkart, Amazon, Zomato, Swiggy, and countless
customer-support platforms like Freshdesk/Zendesk) runs incoming support messages through an
NLP pipeline before a human agent ever sees them: the system normalizes the text, tags parts
of speech and entities, resolves what the customer actually means (a refund request vs. a
delivery complaint vs. a product question), generates a short auto-summary for the agent's
queue, and — crucially for the Indian market — increasingly does this across multiple
languages (Bhashini-style pipelines routinely triage Hindi, Tamil, and Hinglish tickets
alongside English ones). This assignment asks students to build a simplified but *real*
version of that pipeline, using the same techniques covered module-by-module this semester.

## Dataset
Students should assemble (or simulate, if a real dataset isn't accessible) a small set of
**at least 30 customer support messages**, covering a mix of:
- Product/order queries ("Where is my order #4521?")
- Complaints ("The product I received is damaged")
- Refund/return requests ("I want to return this item, it doesn't fit")
- At least 5 messages in Hindi or Hinglish (transliterated Hindi, e.g. "mera order abhi tak nahi aaya")

Suggested sources: publicly available customer-support tweet datasets (e.g. Kaggle's "Customer
Support on Twitter"), or a hand-curated set of realistic messages if no dataset is accessible —
instructor approval required for hand-curated sets.

## Assignment Tasks (mapped to course modules)

### Task 1 — Text Normalization & Morphological Preprocessing (Module 1) — 10 marks
- Tokenize all messages; build a simple FSA-style or two-level-morphology-style normalizer
  that strips common inflectional suffixes (order/orders, deliver/delivered/delivering).
- For the Hindi/Hinglish messages, note (in a short paragraph) what additional morphological
  handling would be needed for a production system, referencing agglutination.

### Task 2 — Word- and Sentence-Level Analysis (Module 2) — 15 marks
- Run POS tagging on every message (compare a rule-based tagger vs. a pretrained tagger, as in
  Practical 3) and report where the rule-based tagger fails.
- Apply spelling correction (noisy-channel style) to at least 5 messages containing typos —
  a realistic feature of real support tickets.
- Extract noun phrases (product names, order numbers) using a simple CFG or regex-based chunker.

### Task 3 — Intent & Meaning Extraction (Module 3) — 20 marks
- Design a small frame schema (e.g., `Intent`, `Product`, `OrderID`, `Sentiment`) and manually
  or semi-automatically populate it for each message — this is the semantic-frame exercise
  from Practical 5, applied to real data.
- For any message containing an ambiguous word (e.g., "return" = give-back vs. come-back), run
  WSD (Lesk or your Naive Bayes classifier) and justify the sense chosen.
- Identify and resolve at least 3 cases of pronoun reference within a multi-sentence ticket
  ("I ordered a phone. It arrived broken.") using the pronoun-resolution approach from Practical 6.

### Task 4 — Auto-Generated Agent Summary (Module 4) — 20 marks
- Build a template-based NLG module that converts each populated frame into a one-line ticket
  summary an agent could scan quickly (e.g., *"Refund request — Order #4521 — item damaged — high priority"*).
- For the Hindi/Hinglish tickets, apply your Practical 8-style toy MT pipeline (or a rule-based
  dictionary + reordering approach) to produce an English gloss alongside the summary, and
  discuss in 2–3 sentences why a production system would need real NMT (e.g., IndicTrans2)
  instead of the toy translator here.

### Task 5 — Ticket Search & Retrieval (Module 5) — 20 marks
- Build an inverted index and a BM25 ranker (as in Practical 9) over your full ticket set.
- Given 3 sample agent queries (e.g., "damaged product complaints", "refund requests today"),
  return and rank the most relevant tickets.
- Evaluate your retrieval using Precision@5 for at least one query where you can manually judge
  relevance.

### Task 6 — Pipeline Justification Report (15 marks)
Write a 1–2 page report, as if documenting this module for a support-tech team, covering:
- The exact order of stages you'd deploy in production (normalization → tagging → intent/frame
  extraction → summarization → indexing) and why that order matters
- Where your pipeline would break on real-world messy data (emojis, code-mixed Hinglish,
  sarcasm) and what module/technique would need to be strengthened
- One paragraph connecting this assignment back to how a modern system might replace several
  of these hand-built stages with a single LLM call, and what would be lost in interpretability
  if it did

## Deliverables
1. A Google Colab notebook (`.ipynb`) with all code and outputs for Tasks 1–5
2. A short technical report (PDF, 1–2 pages) for Task 6
3. (Optional but recommended) A one-slide "before → after" example showing one raw ticket
   transformed all the way to its final ranked-and-summarized form

## Evaluation Rubric

| Criterion | Weight |
|---|---|
| Correctness of implementation (Tasks 1–5) | 55% |
| Depth of technical/industry justification (Task 6) | 25% |
| Code quality, documentation, reproducibility | 10% |
| Presentation clarity (report + optional slide) | 10% |

## Suggested Timeline
- Week 1: Dataset assembly, Tasks 1–2
- Week 2: Task 3
- Week 3: Tasks 4–5
- Week 4: Finalize report and submit

## Module Alignment
This assignment deliberately threads every module (1 through 5) into a single working
pipeline — mirroring how a real support-desk NLP system is actually built — so that by the
end, students have implemented one coherent, end-to-end application rather than five
disconnected labs.

[← Back to index](../index.html)
