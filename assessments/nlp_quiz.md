# NLP Course Quiz — All Modules
### B.Tech Semester V, Natural Language Processing

---

# PART A — 20 Multiple Choice Questions (1 mark each)

1. An FSA is formally defined as the 5-tuple:
 a) (Q, Σ, δ, q0, F)
 b) (V, T, P, S)
 c) (N, Σ, R, S0)
 d) (Q, Σ, Γ, δ, F)

2. Which of the following is mathematically equivalent to a finite-state segmenter used in modern LLM tokenizers?
 a) CFG parsing
 b) Byte-Pair Encoding (BPE)
 c) Word2Vec
 d) BM25 ranking

3. What key limitation of a plain FSA motivates the use of a Recursive Transition Network (RTN)?
 a) FSAs cannot process Unicode text
 b) FSAs cannot represent recursive/nested structure like embedded noun phrases
 c) FSAs are too slow for real-time use
 d) FSAs cannot represent regular languages

4. In an Augmented Transition Network (ATN), "registers" are primarily used to:
 a) Store the final parse tree only
 b) Hold feature values (e.g., number, person) to enforce agreement during parsing
 c) Cache previously seen words for spell-checking
 d) Count the number of transitions taken

5. Which linguistic level is concerned with word-internal structure (stems, affixes)?
 a) Syntactic
 b) Morphological
 c) Semantic
 d) Pragmatic

6. A Context-Free Grammar (CFG) is more expressive than a regular grammar primarily because it can represent:
 a) Ambiguity
 b) Center-embedded/recursive structures
 c) Word frequency
 d) Semantic roles

7. In POS tagging, the Viterbi algorithm is used to:
 a) Train word embeddings
 b) Efficiently find the most probable tag sequence in an HMM
 c) Build an inverted index
 d) Compute BLEU scores

8. The "noisy channel model" used in spelling correction combines:
 a) Only a language model
 b) A language model (P(w)) and an error/channel model (P(observed|w))
 c) Only an edit-distance heuristic
 d) A neural network with no probabilistic basis

9. PP-attachment ambiguity, as in "I saw the man with the telescope," is an example of:
 a) Lexical ambiguity
 b) Syntactic (structural) ambiguity
 c) Pragmatic ambiguity
 d) Morphological ambiguity

10. Word Sense Disambiguation (WSD) using the Lesk algorithm primarily relies on:
 a) Overlap between a word's sense definitions and its surrounding context
 b) Neural attention weights
 c) Frequency of the word in a corpus
 d) Part-of-speech tag alone

11. A semantic frame representation for "The bank approved the loan" would typically capture:
 a) Only the syntactic tree
 b) Roles such as Approver, Decision, and Item
 c) The phonetic transcription
 d) The document's retrieval score

12. Which of the following best describes lexical cohesion in discourse analysis?
 a) Grammatical agreement between subject and verb
 b) Repeated or related words linking sentences together in a text
 c) The frequency of stop words
 d) The number of named entities in a paragraph

13. In the classical NLG pipeline, "content determination" refers to:
 a) Choosing the surface words and syntax
 b) Deciding WHAT information/facts to communicate
 c) Formatting the final text for display
 d) Translating text into another language

14. Google Translate's 2016 architecture shift is best described as moving from:
 a) Rule-based MT to Statistical MT
 b) Statistical MT (SMT) to Neural MT (NMT)
 c) Neural MT to Rule-based MT
 d) BM25 retrieval to embedding retrieval

15. IBM Model 1, used for word alignment in Statistical MT, is trained using:
 a) Gradient descent on a neural network
 b) The Expectation-Maximization (EM) algorithm
 c) Breadth-first search
 d) The Viterbi algorithm exclusively

16. Which characteristic of Indian languages most directly complicates direct English-to-Hindi machine translation word ordering?
 a) Indian languages use a different alphabet only
 b) Hindi's SOV word order versus English's SVO word order
 c) Indian languages have no punctuation
 d) Indian languages lack a written form

17. BM25, used for ranking in Elasticsearch, Solr, and OpenSearch, is fundamentally a:
 a) Neural embedding model
 b) Probabilistic term-weighting ranking function
 c) Grammar-checking algorithm
 d) POS tagging model

18. In Information Retrieval evaluation, Mean Average Precision (MAP) is computed by:
 a) Averaging precision values at each point a relevant document is retrieved, across queries
 b) Counting the total number of documents in the collection
 c) Measuring only the top-1 retrieved document's relevance
 d) Averaging the inverted index size across queries

19. WordNet's Wu-Palmer similarity measure computes semantic similarity based on:
 a) String edit distance between words
 b) The depth of the two synsets and their lowest common hypernym in the taxonomy
 c) Word frequency in a reference corpus
 d) Cosine similarity of TF-IDF vectors

20. FrameNet-style semantic role labeling is most directly used in industry for:
 a) Speech-to-text transcription
 b) Event extraction from financial news and legal documents
 c) Compressing images
 d) Building inverted indexes

---

# PART B — 5 Fill in the Blanks (1 mark each)

1. The two-level morphology model relates the __________ level (underlying morphemes) to the __________ level (the actual spelled-out word form).

2. A parser that uses probabilities attached to grammar rules to rank competing parses is called a __________.

3. In discourse analysis, the process of determining which noun phrase a pronoun like "she" or "it" refers to is called __________.

4. The standard automatic evaluation metric for machine translation quality, based on n-gram overlap with reference translations, is called __________.

5. In Information Retrieval, a data structure mapping each term to the list of documents containing it is called an __________.

---

# PART C — 5 True/False (1 mark each)

1. A Recursive Transition Network (RTN) can represent nested/recursive syntactic structure that a plain FSA cannot. **(True/False)**

2. The Lesk algorithm for Word Sense Disambiguation requires a labeled training corpus of sense-tagged sentences to function. **(True/False)**

3. BM25 generally outperforms simple Boolean retrieval by incorporating term frequency and document length normalization into a ranking score. **(True/False)**

4. IBM Model 1 assumes a fixed, monotonic word order between the source and target languages. **(True/False)**

5. Precision measures the fraction of retrieved documents that are relevant, while Recall measures the fraction of relevant documents that were retrieved. **(True/False)**

---

# PART D — Match the Following (5 pairs, 1 mark each)

| Column A | Column B |
|---|---|
| 1. IBM Model 1 | A. Ranking function used by Elasticsearch/Solr |
| 2. ATN Register | B. Word-alignment probability estimated via EM |
| 3. BM25 | C. WordNet-based semantic distance measure |
| 4. Wu-Palmer Similarity | D. Feature-value slot enforcing subject-verb agreement |
| 5. Lesk Algorithm | E. Word Sense Disambiguation via definition-context overlap |

---

# ANSWER KEY (For Instructor Use)

**Part A (MCQ):**
1-a, 2-b, 3-b, 4-b, 5-b, 6-b, 7-b, 8-b, 9-b, 10-a, 11-b, 12-b, 13-b, 14-b, 15-b, 16-b, 17-b, 18-a, 19-b, 20-b

**Part B (Fill in the blanks):**
1. Lexical; Surface
2. PCFG (Probabilistic Context-Free Grammar) parser / Viterbi parser
3. Coreference resolution (anaphora resolution)
4. BLEU
5. Inverted index

**Part C (True/False):**
1. True
2. False (the classic Lesk algorithm is knowledge-based, using dictionary definitions/glosses, not a labeled training corpus)
3. True
4. False (IBM Model 1 explicitly does NOT model word order/distortion — that is added in later IBM Models, e.g. Model 2)
5. True

**Part D (Match the following):**
1-B, 2-D, 3-A, 4-C, 5-E

[← Back to index](../index.html)
