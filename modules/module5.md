# Module 05 — Information Retrieval & Lexical Resources
### IR Models · Evaluation · WordNet · FrameNet · Stemmers

**Course:** Natural Language Processing (B.Tech, Semester V)
[← Back to course map](../index.html#m5)

---

## 1. Inverted Index (1 lecture)

**Content**
- Why linear scanning doesn't scale: motivating the inverted index structure
- Building an inverted index: term → posting list of documents (and positions)
- Index construction pipeline: tokenization → normalization → indexing

**Industry Illustration**
- The inverted index is the foundational data structure behind every major search engine (Google, Bing) and every enterprise search product (Elasticsearch, Solr, OpenSearch).

## 2. Retrieval Models: Boolean, Vector Space, Probabilistic (2 lectures)

**Content**
- **Boolean retrieval**: exact-match queries with AND/OR/NOT — simple but rigid
- **Vector Space Model (VSM)**: TF-IDF weighting, cosine similarity for ranked retrieval
- **Probabilistic retrieval — BM25**: relevance ranking grounded in probability theory, and why it outperforms plain TF-IDF in practice

**Industry Illustration**
- **BM25** is the default ranking function inside **Elasticsearch, Solr, and OpenSearch** — one of the most widely deployed scoring functions in production software today.

## 3. LSI and Dense/Embedding Retrieval (2 lectures)

**Content**
- **Latent Semantic Indexing (LSI)**: dimensionality reduction (SVD) over the term-document matrix to capture latent topics and handle synonymy
- Modern **dense/embedding-based retrieval**: encoding queries and documents into a shared vector space, retrieving by nearest-neighbor similarity
- Comparing sparse (BM25) vs. dense (embedding) retrieval — and where hybrid approaches fit

**Industry Illustration**
- **Embedding-based retrieval** is the backbone of every modern **RAG (Retrieval-Augmented Generation)** pipeline behind chat assistants that search internal documents — this is the single most in-demand IR skill in current NLP job postings.

## 4. Evaluation: Precision, Recall, MAP (1 lecture)

**Content**
- Precision and Recall for retrieval; the precision-recall trade-off
- **Mean Average Precision (MAP)** and other ranked-retrieval evaluation metrics
- Building a small evaluation harness for a retrieval system

**Industry Illustration**
- Search-quality teams at any company running a product search or document search feature track these exact metrics (often alongside click-through data) to evaluate ranking changes before deployment.

## 5. WordNet Similarity (1 lecture)

**Content**
- Recap of WordNet's structure (from Module 3) with a focus on **similarity measures**: path-based (shortest path in the hypernym hierarchy), information-content-based (Resnik, Lin)
- Applications: query expansion, semantic textual similarity tasks

## 6. FrameNet (1 lecture)

**Content**
- Frame semantics: representing meaning via evoked "frames" with semantic roles (frame elements)
- Comparing FrameNet's frame-based representation to WordNet's relation-based representation

**Industry Illustration**
- **FrameNet-style semantic roles** still power **event extraction** from financial news and legal documents in production information-extraction systems today.

## 7. Stemmers & POS Taggers (1 lecture — synthesis)

**Content**
- Comparing stemming algorithms: **Porter, Lancaster, Snowball** — aggressiveness and use-case trade-offs
- Recap and tie-together of POS tagging (Module 2) as a component that feeds both IR (index-time normalization) and lexical-resource lookup

---

## Suggested Labs — Module 05

| # | Practical | Concepts Covered |
|---|-----------|-------------------|
| P9 | **Information Retrieval** — inverted index, Boolean/VSM/BM25 ranking, LSI & embedding-based semantic search, Precision/Recall/F1/MAP evaluation | Inverted index, Retrieval models, Evaluation |
| P10 | **Lexical Resources** — WordNet similarity measures, real FrameNet frame/role exploration, Porter/Lancaster/Snowball stemmer comparison, a POS tagger trained from scratch | WordNet, FrameNet, Stemmers, POS tagging |

## Future Leads for Students
- Learn **vector databases** (FAISS, Pinecone, pgvector) and how they scale the dense retrieval built in this module.
- Study **hybrid search** — combining BM25 with embeddings — the pattern used in most production RAG systems.
- Explore building **lexical resources for Indian languages**, extending WordNet/FrameNet-style structures.

## References
1. Christopher D. Manning, Prabhakar Raghavan, Hinrich Schütze, *Introduction to Information Retrieval*, Cambridge University Press.
2. Charles J. Fillmore, *Frame Semantics and the Nature of Language*, Annals of the NY Academy of Sciences.
3. Karen Sparck Jones, *A Statistical Interpretation of Term Specificity and Its Application in Retrieval* — foundational TF-IDF paper.

---

## Closing: Five Stages, One Machine

Every module in this course is a stage the same pipeline runs, in order, on every sentence a real system processes — from a search box, a translation request, or a chat message. Understanding where a model sits in that pipeline is the fastest way to reason about what it can and can't do.

[← Back to course map](../index.html)
