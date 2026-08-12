# Module 03 — Semantic Analysis
### Meaning Representation · WSD · Discourse · Knowledge Reasoning

**Course:** Natural Language Processing (B.Tech, Semester V)
[← Back to course map](../index.html#m3)

---

## 1. Meaning Representation (1–2 lectures)

**Content**
- Why syntax alone isn't meaning: the gap between "correct sentence structure" and "what the sentence asserts"
- Representation schemes: First-Order Logic (FOL) predicates, semantic/frame representations, event-based representations
- Compositional semantics: building sentence meaning from word meaning + syntactic structure

**Industry Illustration**
- **Voice assistants** parse an instruction like "turn off bedroom lights" into a semantic frame (intent = turn_off, device = lights, location = bedroom) before any action is taken — this is meaning representation in production.

## 2. Lexical Semantics (1–2 lectures)

**Content**
- Word-meaning relations: synonymy, antonymy, hyponymy/hypernymy, meronymy
- **WordNet** as a structured lexical database encoding these relations; synsets and semantic hierarchies
- Using lexical relations for tasks like similarity computation and query expansion

**Industry Illustration**
- WordNet-derived similarity measures still underpin components of search relevance, thesaurus features in writing tools, and educational NLP applications.

## 3. Ambiguity (1 lecture)

**Content**
- Taxonomy of ambiguity: lexical (word senses), syntactic (structural), semantic (scope), pragmatic (context-dependent meaning)
- Why ambiguity resolution is the central challenge of the semantic-analysis stage

**Industry Illustration**
- Every machine translation and question-answering system must resolve ambiguity before producing correct output — ambiguity handling quality is a major differentiator between production-grade and toy NLP systems.

## 4. Word Sense Disambiguation (2 lectures)

**Content**
- The WSD problem: choosing the correct sense of a polysemous word given context
- Knowledge-based approaches: the **Lesk algorithm** (overlap between context and sense definitions)
- Supervised approaches: feature-based classifiers (e.g., Naive Bayes) trained on sense-labeled data

**Industry Illustration**
- **Google Translate** silently performs WSD every time it must pick a target-language word for an ambiguous source word (e.g., translating "bank" correctly as riverbank vs. financial institution based on context).

## 5. Cohesion & Reference Resolution (1–2 lectures)

**Content**
- Lexical cohesion: how a text "hangs together" via repeated/related terms
- Reference resolution: pronoun resolution, anaphora, cataphora — rule-based approaches (e.g., Hobbs' algorithm concept) as a foundation

**Industry Illustration**
- Customer-support chatbots and document-summarization tools depend on reference resolution to correctly track "it," "they," "this" across a conversation or paragraph.

## 6. Discourse Coherence (1 lecture)

**Content**
- What makes a sequence of sentences a coherent discourse rather than a random list
- **Rhetorical Structure Theory (RST)**-style discourse relations: elaboration, contrast, cause, etc.

**Industry Illustration**
- Automated essay-scoring and summarization-quality evaluation tools use discourse-coherence signals to judge text quality beyond grammar correctness.

## 7. Knowledge Representation & Reasoning (2 lectures)

**Content**
- Semantic networks: nodes and labeled relations for encoding world knowledge
- Inheritance and **forward-chaining reasoning** over a knowledge base
- Connecting linguistic meaning representation (from earlier in this module) to a queryable knowledge structure

**Industry Illustration**
- **Google's Knowledge Graph** and **Wikidata** are web-scale semantic networks built on the same inheritance-and-reasoning principles taught in this module, just at massive scale.

---

## Suggested Labs — Module 03

| # | Practical | Concepts Covered |
|---|-----------|-------------------|
| P5 | **Semantic Analysis** — FOL & frame representations, WordNet lexical relations, ambiguity typology, Lesk WSD (hand-built + NLTK) and a Naive Bayes sense classifier | Meaning representation, WordNet, WSD |
| P6 | **Discourse & Knowledge** — lexical cohesion detection, rule-based pronoun resolution, RST-style discourse tagging, semantic networks + forward-chaining reasoning | Cohesion, Reference resolution, Discourse, Knowledge reasoning |

## Future Leads for Students
- Study how **contextual embeddings (BERT)** implicitly solve WSD without an explicit sense inventory.
- Explore **neural coreference resolution** and the Winograd Schema Challenge as a reasoning benchmark.
- Look into **ontology engineering** and knowledge-graph construction as a research/industry track.

## References
1. Daniel Jurafsky and James H. Martin, *Speech and Language Processing*, Chapters on Semantics, WSD, and Discourse.
2. George A. Miller et al., *WordNet: An Electronic Lexical Database*, MIT Press.
3. William Mann and Sandra Thompson, *Rhetorical Structure Theory: Toward a Functional Theory of Text Organization*.
