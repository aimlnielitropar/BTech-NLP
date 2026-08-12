# Module 01 — Introduction
### Computational Framework · Finite State Automata · RTN / ATN

**Course:** Natural Language Processing (B.Tech, Semester V)
[← Back to course map](../index.html#m1)

---

## 1. What is NLP: The Three Pillars (1 lecture)

**Content**
- NLP as the intersection of linguistics and computation; why "understanding language" is fundamentally a search/computation problem
- The three-pillar framework every NLP system is built from: **Lexicon** (the vocabulary/word-store), **Algorithm** (the procedure operating on it), **Data structure** (how linguistic knowledge is represented — tries, automata, graphs, vectors)
- A brief map of NLP's history: symbolic/rule-based era → statistical era → neural/transformer era → LLMs, and where classical formalisms (this module) still sit underneath modern systems

**Industry Illustration**
- Every major NLP product — from a spell-checker to a transformer-based chatbot — is still, structurally, a lexicon + an algorithm + a data structure; what changes is *how* those three pieces are implemented (hand-written rules vs. learned weights).

## 2. Finite State Automata (2 lectures)

**Content**
- Formal definition: FSA = (Q, Σ, δ, q₀, F) — states, alphabet, transition function, start state, accepting states
- Deterministic (DFA) vs Non-deterministic (NFA) automata; equivalence
- Finite State Transducers (FST) — automata that *produce output*, not just accept/reject, and why this matters for language (an FST maps a surface word to its underlying morphemes, and vice versa)
- Regular languages and their relevance/limits for natural language (why regular languages can't capture everything about syntax — motivates CFGs in Module 2)

**Industry Illustrations**
- Modern **LLM tokenizers** (Byte-Pair Encoding, WordPiece, SentencePiece — used in GPT, Gemini, Claude) are, mathematically, finite-state segmenters: the direct computational descendant of the FSA formalism taught here.
- **Voice assistants** (Alexa, Siri, Google Assistant) chain Weighted Finite State Transducers (WFSTs) together for pronunciation modeling and language modeling in their speech pipelines.
- Regex-based input validation and text normalization pipelines used across virtually every production NLP system as a pre-processing stage.

## 3. Morphological Analysis via FSA (1–2 lectures)

**Content**
- Word formation: inflectional morphology (boy → boys) vs derivational morphology (nation → national)
- Building a morphological analyzer as an FST: mapping surface forms to lemma + grammatical features
- Applying the framework to **English** and to **Indian languages** — highlighting why agglutinative, morphologically rich languages (Hindi, Tamil, Telugu, etc.) need richer finite-state morphology than English

**Industry Illustration**
- **AI4Bharat / Bhashini** (India's national language AI mission) begins Indian-language NLP pipelines with exactly this finite-state morphological analysis layer before any deep learning model runs — because Indian languages' rich morphology means a word can carry information an English sentence would spread across several words.

## 4. Levels of Linguistic Analysis (1 lecture)

**Content**
- The standard analysis stack: **Morphological → Syntactic → Semantic → Pragmatic (→ Discourse)**
- What each level answers: word structure, sentence structure, literal meaning, meaning-in-context
- Framing this stack as the "pipeline" the rest of the course (Modules 2–5) walks through level by level

**Industry Illustration**
- Any conversational AI system (a chatbot, a voice assistant) must implicitly pass an utterance through all these levels before it can act — a request like "book me the earliest flight" needs morphological parsing, syntactic structure, semantic intent extraction, and pragmatic context (whose calendar, which airport) to be handled correctly.

## 5. Recursive Transition Networks (RTN) and Augmented Transition Networks (ATN) (2 lectures)

**Content**
- RTN: extending finite-state networks with the ability to call other networks recursively — enabling representation of recursive/nested grammatical structure (e.g., nested noun phrases) that plain FSAs cannot capture
- ATN: adding registers/conditions/actions to an RTN — allowing feature-checking (e.g., subject-verb agreement) during parsing
- Why ATNs were historically important as an early practical parsing formalism, and their relationship to modern feature-based grammars

**Industry Illustration**
- Grammar/agreement-checking logic in early rule-based writing assistants and syntax-highlighters for constrained-language systems (e.g., aviation's Simplified Technical English checkers) still resembles ATN-style condition-action parsing.

## 6. Machine Translation as an Application (1 lecture — preview)

**Content**
- A first, high-level look at MT as a motivating application that touches every level of the pipeline (deep dive comes in Module 4)
- Framing: why MT is often used as the "hardest problem" benchmark for NLP systems, since it requires correct analysis *and* correct generation

**Industry Illustration**
- Google Translate's 2016 shift from Statistical MT to Neural MT is one of the most public NLP architecture transitions in industry — introduced early here, revisited in full in Module 4.

---

## Suggested Labs — Module 01

| # | Practical | Concepts Covered |
|---|-----------|-------------------|
| P1 | **FSA, RTN & ATN** — build an English + Hindi morphological FSA, a recursive prefix-matching network, an agreement-checking ATN, and a spelling-detection application | FSA/FST, RTN, ATN |
| P2 | **Levels of Analysis + MT** — run one sentence through morphological → syntactic → semantic → pragmatic analysis, then apply a translation step as an applied example | Levels of analysis, MT (intro) |

## Future Leads for Students
- Study **Weighted Finite State Transducers (WFSTs)** — the production-grade version of the FSTs built by hand in this module.
- Explore agglutinative-morphology research for Indian languages via AI4Bharat's open tooling.
- Trace how modern **BPE/SentencePiece tokenizer training** connects directly back to classical FSA theory covered here.

## References
1. Daniel Jurafsky and James H. Martin, *Speech and Language Processing*, 3rd ed. (draft), Chapters on Regular Expressions, FSAs, and Morphology.
2. James Allen, *Natural Language Understanding*, 2nd Edition, Benjamin/Cummings.
3. Akshar Bharati, Vineet Chaitanya, Rajeev Sangal, *Natural Language Processing: A Paninian Perspective*, PHI Learning — for the Indian-language framing.
