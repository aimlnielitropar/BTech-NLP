# Module 04 — Natural Language Generation
### NLG Architecture · Machine Translation · Indian Languages

**Course:** Natural Language Processing (B.Tech, Semester V)
[← Back to course map](../index.html#m4)

---

## 1. NLG Pipeline Architecture (2 lectures)

**Content**
- The classical NLG pipeline: **content determination → discourse planning → sentence aggregation → lexicalization → referring expression generation → linguistic realization**
- What each stage decides, with a worked example (e.g., generating a weather report sentence from structured data)
- Representations used at each stage: content plans, discourse trees, realized text

**Industry Illustration**
- **Automated journalism**: the Associated Press generates thousands of earnings reports and sports recaps via Wordsmith/Arria-style NLG pipelines that follow exactly this content-determination → realization structure.

## 2. Generation Tasks & Representations (1 lecture)

**Content**
- Common NLG task types: data-to-text, summarization-as-generation, dialogue response generation
- Template-based generation vs. statistical/neural generation — trade-offs in controllability vs. fluency

## 3. Applications of NLG (1 lecture)

**Content**
- Survey of real deployments: report generation, chatbot responses, product description generation, accessibility (text-to-speech content preparation)

**Industry Illustration**
- E-commerce platforms auto-generate product descriptions and summaries at scale using data-to-text NLG pipelines feeding into further language-model refinement.

## 4. Problems in Machine Translation (1–2 lectures)

**Content**
- MT-specific challenges: lexical ambiguity, structural divergence between languages, idiomatic expressions, word-order differences
- Why MT is a strong "stress test" for an NLP system, requiring correct analysis (Modules 1–3) *and* correct generation

## 5. Characteristics of Indian Languages (1–2 lectures)

**Content**
- Key linguistic properties relevant to MT: agglutinative morphology, relatively free word order, SOV (Subject-Object-Verb) canonical order vs. English's SVO
- Why generic, English-centric MT approaches under-perform on Indian languages, and what adaptations are needed

**Industry Illustration**
- **Bhashini** and **AI4Bharat's IndicTrans2** exist specifically because generic NMT systems under-perform on agglutinative, SOV Indian languages — this module's content is the linguistic justification for why India needed its own MT research program.

## 6. MT Approaches: RBMT / SMT / NMT (2–3 lectures)

**Content**
- **Rule-Based MT (RBMT)**: transfer-based and interlingua approaches
- **Statistical MT (SMT)**: word/phrase alignment, IBM Models (esp. IBM Model 1 with Expectation-Maximization), phrase-based SMT
- **Neural MT (NMT)**: sequence-to-sequence models, attention mechanisms, the Transformer architecture (conceptual bridge to modern LLM-based translation)
- Evaluation: **BLEU** score mechanics and its limitations

**Industry Illustration**
- **Google Translate's 2016 switch from SMT to NMT** is the exact IBM Model 1 → neural transition this module walks through — one of the most publicly documented architecture migrations in NLP industry history.

---

## Suggested Labs — Module 04

| # | Practical | Concepts Covered |
|---|-----------|-------------------|
| P7 | **Natural Language Generation** — full content-determination → realization pipeline on live weather data, template NLG, statistical n-gram generation, real-world NLG survey | NLG pipeline stages |
| P8 | **Machine Translation** — MT problem taxonomy, Indian-language morphology, rule-based + IBM Model 1 (EM from scratch) + neural MT, BLEU evaluation | RBMT, SMT, NMT, Evaluation |

## Future Leads for Students
- Explore how **LLMs now perform content-determination and realization jointly**, effectively collapsing the classic NLG pipeline into a single generation step.
- Study **low-resource NMT techniques** for Indian language pairs, and contribute to Bhashini's open datasets.
- Learn modern MT evaluation beyond BLEU — **chrF** and **COMET**, both used in WMT shared tasks.

## References
1. Ehud Reiter and Robert Dale, *Building Natural Language Generation Systems*, Cambridge University Press.
2. Philipp Koehn, *Statistical Machine Translation*, Cambridge University Press.
3. Vaswani et al., *Attention Is All You Need*, NeurIPS 2017 — foundational Transformer paper underlying modern NMT.
4. AI4Bharat, *IndicTrans2* project documentation — for Indian-language MT case study.
