# Module 02 — Word Level & Syntactic Analysis
### Regex · POS Tagging · CFG · Probabilistic Parsing

**Course:** Natural Language Processing (B.Tech, Semester V)
[← Back to course map](../index.html#m2)

---

## 1. Regular Expressions for Text Processing (1 lecture)

**Content**
- Regex syntax as applied to text: character classes, quantifiers, groups, back-references
- Practical text-processing tasks: tokenization assistance, pattern extraction (dates, emails, entities), simple text cleaning
- Limits of regex — why it can't capture recursive/hierarchical structure (bridges into CFG later in this module)

**Industry Illustration**
- Log-parsing, form-validation, and lightweight entity extraction in production systems (e.g., extracting phone numbers/emails from support tickets) almost always starts with hand-written regex before any ML model is invoked.

## 2. Morphological Parsing Revisited: Two-Level Morphology (1 lecture)

**Content**
- Two-level morphology: separating the *lexical* level (underlying morphemes) from the *surface* level (spelled form), connected by orthographic rules
- Handling spelling-change rules (e.g., "study" + "s" → "studies") as finite-state rule application (link back to Module 1's FST)

**Industry Illustration**
- Search-engine query expansion (Google, Bing) relies on morphological normalization structurally identical to a two-level parser, so a search for "running" also matches documents containing "run" or "ran."

## 3. Spelling Correction (1 lecture)

**Content**
- The noisy channel model: treating a misspelling as a "corrupted" version of an intended word
- Edit distance (Levenshtein) as the core similarity metric
- Candidate generation and ranking (frequency-weighted candidates)

**Industry Illustration**
- Mobile keyboards (**Gboard, SwiftKey**) run noisy-channel-style spelling correction on-device in real time, balancing edit-distance candidates against a language model for the most likely intended word.

## 4. POS Tagging: Rule-Based, HMM, Viterbi (2–3 lectures)

**Content**
- The POS tagging problem: assigning a grammatical category to each token in context
- Rule-based tagging: hand-written disambiguation rules
- Statistical tagging with **Hidden Markov Models**: states as tags, emission and transition probabilities
- The **Viterbi algorithm**: dynamic programming for the most probable tag sequence
- Evaluation: tagging accuracy, handling unknown words

**Industry Illustration**
- Every downstream NLP task — parsing, information extraction, question answering — depends on a POS-tagging layer; this is one of the most "invisible but universal" components in production NLP stacks.

## 5. Context-Free Grammars (2 lectures)

**Content**
- CFG formalism: non-terminals, terminals, production rules, start symbol
- Writing a small CFG for English sentence structure; ambiguity in CFGs (e.g., PP-attachment)
- Chomsky Normal Form and its role in parsing algorithms

**Industry Illustration**
- Even though most production parsers today are neural, CFG-style grammatical formalisms remain the backbone of formal grammar checking tools and domain-specific language parsers (e.g., parsing structured commands in voice assistants).

## 6. Constituency & Probabilistic Parsing (2 lectures)

**Content**
- Parsing algorithms: top-down, bottom-up, and chart parsing (CYK algorithm) for efficient CFG parsing
- **Probabilistic CFGs (PCFG)**: attaching probabilities to rules to rank competing parses and resolve ambiguity
- Constituency trees vs. the dependency-parsing alternative (introduced here, elaborated in "Future Leads")

**Industry Illustration**
- **spaCy's dependency parser** — used across thousands of production NLP pipelines — is the direct industrial successor to the constituency/PCFG parsers built by hand in this module; understanding PCFG ranking makes spaCy's parser output far more interpretable.

## 7. Machine-Readable Dictionaries (1 lecture)

**Content**
- Structuring lexical entries for computational use: POS, sense definitions, example usage, morphological features
- Precursor to WordNet (Module 3/5) — how machine-readable dictionaries evolve into structured lexical-semantic resources

**Industry Illustration**
- Grammar and style-checking tools (e.g., Grammarly's rule-based layer) rely on machine-readable dictionaries merged with statistical models for suggestions.

---

## Suggested Labs — Module 02

| # | Practical | Concepts Covered |
|---|-----------|-------------------|
| P3 | **Word-Level Analysis** — regex extraction, two-level FSA morphology, noisy-channel spelling correction, rule-based → HMM/Viterbi → pretrained POS tagging | Regex, Morphology, Spelling correction, POS tagging |
| P4 | **Syntactic Analysis** — CFG + chart parsing, PP-attachment ambiguity, PCFG ranking, spaCy dependency parsing, WordNet, RTN-as-recursive-descent parser | CFG, PCFG, Dependency parsing |

## Future Leads for Students
- Move from constituency parsing to **dependency and transition-based neural parsing** (spaCy, Stanza).
- Study **CRF and BiLSTM-CRF taggers** as the statistical/neural successors to HMM/Viterbi tagging.
- Explore treebank annotation projects for low-resource Indian languages.

## References
1. Daniel Jurafsky and James H. Martin, *Speech and Language Processing*, Chapters on POS Tagging, HMMs, and Syntactic Parsing.
2. Christopher D. Manning and Hinrich Schütze, *Foundations of Statistical Natural Language Processing*, MIT Press.
3. spaCy documentation — dependency parsing architecture (industry reference implementation).
