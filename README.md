# Natural Language Processing — B.Tech Semester V

Course materials for **Natural Language Processing**, taught as one continuous five-stage
pipeline: every sentence a real system processes moves through morphology → syntax →
semantics → generation → retrieval, and each module of this course is one stage of that
pipeline.

▶ **[Open the course site](https://<your-username>.github.io/<your-repo-name>/)** (once GitHub Pages is enabled — see below), or open `index.html` directly.

---

## The Five-Stage Pipeline

| Module | Stage | Core Topics |
|---|---|---|
| 01 | **Introduction** | Computational framework, FSA, RTN, ATN, levels of analysis, MT preview |
| 02 | **Word Level & Syntactic Analysis** | Regex, morphological parsing, spelling correction, POS tagging, CFG, probabilistic parsing |
| 03 | **Semantic Analysis** | Meaning representation, lexical semantics, ambiguity, WSD, discourse, knowledge reasoning |
| 04 | **Natural Language Generation** | NLG pipeline architecture, generation tasks, MT (RBMT/SMT/NMT), Indian languages |
| 05 | **Information Retrieval & Lexical Resources** | Inverted index, Boolean/VSM/BM25/LSI, IR evaluation, WordNet, FrameNet, stemmers |

---

## Repository Structure

```
.
├── index.html                                     # Course landing page — hover the hero
│                                                    # sentence to see it move through all 5 stages
├── README.md                                       # You are here
├── modules/
│   ├── module1.md                                  # Introduction
│   ├── module2.md                                  # Word Level & Syntactic Analysis
│   ├── module3.md                                  # Semantic Analysis
│   ├── module4.md                                  # Natural Language Generation
│   └── module5.md                                  # Information Retrieval & Lexical Resources
├── notebooks/
│   ├── NLP_Practical1_FSA_RTN_ATN.ipynb
│   ├── NLP_Practical2_Levels_and_MT.ipynb
│   ├── NLP_Practical3_WordLevel_Analysis.ipynb
│   ├── NLP_Practical4_Syntactic_Analysis.ipynb
│   ├── NLP_Practical5_Semantic_Analysis.ipynb
│   ├── NLP_Practical6_Discourse_and_Knowledge.ipynb
│   ├── NLP_Practical7_NLG.ipynb
│   ├── NLP_Practical8_Machine_Translation.ipynb
│   ├── NLP_Practical9_Information_Retrieval.ipynb
│   └── NLP_Practical10_Lexical_Resources.ipynb
└── assessments/
    ├── nlp_quiz.md                                 # 20 MCQ + 5 Fill-in-blank + 5 T/F + 5 Match-the-following
    └── nlp_mini_assignment.md                       # Multilingual customer-support ticket triage (industry use case)
```

---

## How to Use This Repository

### For students
1. Start at `index.html` (or the GitHub Pages link above). Hover the tokens in the hero
   sentence to see which module/color each word belongs to.
2. Work through Modules 1–5 in order — each module page has the full lecture-by-lecture
   content, industry takeaways, and "future leads" for further study.
3. Every module links directly to its Colab notebook(s) — click a practical card and use
   **File → Save a copy in Drive** in Colab to get your own editable copy.
4. Attempt the quiz and the mini-assignment in `assessments/` once you've worked through
   the relevant modules.

### For instructors
- All content is plain Markdown/HTML — fork or clone the repo and edit directly.
- Each notebook uses only `pip install`-able packages (`nltk`, `spacy`, `scikit-learn`,
  `rank_bm25`) and NLTK's built-in corpora — no external API keys required, so every
  practical runs standalone in a fresh Colab session.
- The mini-assignment in `assessments/nlp_mini_assignment.md` is deliberately built to
  thread all five modules into one working system (a support-ticket triage pipeline) —
  swap in a different domain dataset each semester to keep it fresh.

### Enabling GitHub Pages (optional, for a hosted course site)
1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, select the `main` branch and `/ (root)` folder.
4. Your site will be live at `https://<username>.github.io/<repo-name>/` within a few
   minutes, with `index.html` as the homepage.

*(Note: GitHub Pages serves `.md` files as plain text, not rendered Markdown, since there's
no static-site generator in this repo. Students browsing via the regular GitHub UI will see
them rendered normally either way.)*

---

## Industry Grounding

Every module page ties its classical-NLP techniques to a current production system —
LLM tokenizers as finite-state segmenters, spaCy's dependency parser as the industrial
successor to PCFG parsing, BM25 as the default Elasticsearch/Solr ranker, and AI4Bharat's
Bhashini/IndicTrans2 as the ongoing Indian-language answer to problems classical MT theory
predicts. The goal throughout is for students to leave each module able to name the real
system their technique grew into.

---

## License / Usage

Course material prepared for internal teaching use. Students may fork and use for personal
study; please retain attribution if redistributing.
