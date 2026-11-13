---
title: PT-F2 Reflection

---

### [🏠 Home](../index.md) | [💻 Projects](../projects.md) | [📚 ITC-C506 Coursework](../itc-c506.md) | [📚 ITC-C508 Coursework](../itc-c508.md) > **[PT-F2 Reflection](./itc-c508/reflection/PT-F2Reflection.md)**

---

This second part of the chunking experiment report details our systematic evaluation of twelve different chunking configurations (C1 through C12) using Republic Act No. 9710 (The Magna Carta of Women) as our benchmark dataset. Testing various combinations of chunk sizes (ranging from 300 to 1,500 characters) and overlap margins (ranging from 0 to 300 characters) across nine verified test questions provided a clear look at how text segmentation directly impacts retrieval accuracy.

Analyzing the results showed that smaller chunk sizes (like the 300-character windows in C1–C3) frequently caused boundary fragmentation, splitting interconnected legal clauses and conditional requirements across separate blocks. This led to lower ranking metrics and dropped recall on multi-section queries. By contrast, larger configurations like C8 (1,000 characters, 0 overlap) and C12 (1,500 characters, 300 overlap) preserved complete statutory sections, achieving top-tier Mean Reciprocal Rank (MRR@3) scores of 0.944. Ultimately, Configuration C12 proved to be the most optimal strategy, balancing high precision (0.593), perfect evidence recall (1.000), superior ranking efficiency (0.944), and computational economy by generating only 54 total chunks.

Looking at what could be improved, while Configuration C12 performed exceptionally well on a structured legislative text like the Magna Carta of Women, fixed-character chunking inherently struggles when applied to documents with dense, highly cross-referenced definitions or varying prose structures. A fixed 1,500-character window can still occasionally cut off an exception clause or a supporting proviso if it falls right at the boundary. Future improvements could explore semantic chunking algorithms or late-split techniques that segment text based on natural legal article boundaries rather than arbitrary character counts.

Overall, this experiment provided solid empirical evidence showing that precise hyperparameter tuning of chunk size and overlap is just as critical to a RAG pipeline's success as the embedding model or the language model itself.
