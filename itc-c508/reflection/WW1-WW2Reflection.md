---
title: WWi-WW2 Reflection

---

### [🏠 Home](../index.md) | [💻 Projects](../projects.md) | [📚 ITC-C506 Coursework](../itc-c506.md) | [📚 ITC-C508 Coursework](../itc-c508.md) > **[WW1-WW2 Reflection](./itc-c508/reflection/WW1-WW2Reflection.md)**

---

This group experimentation report focuses on optimizing and benchmarking our RAG chatbot built on the Barangay VAW Desk Handbook (2023). Building directly on our individual chunking experiments, the group evaluated twelve configurations and identified Configuration C8 (800-character chunk size, 80-character overlap, and a Top-K of 3) as the optimal setting. This configuration achieved a Precision@3 of 0.6296, Recall@3 of 0.8611, and an MRR@3 of 0.9259 across 206 total chunks, striking the right balance by keeping procedural and legal steps within single passages without over-fragmenting text or introducing noise.

To measure computational efficiency, the optimized RAG pipeline was benchmarked across small (400/50), medium (800/80), and large (1,200/150) settings on both Google Colab CPU and NVIDIA T4 GPU runtimes. The results confirmed that GPU acceleration drastically slashed execution time without altering retrieval metrics. For our recommended C8 configuration, total response time dropped from 16.32 seconds on the CPU down to 3.14 seconds on the GPU, while indexing speed improved by roughly 5.13x (from 26.40 s to 5.15 s) and generation speed improved by 5.23x (from 16.20 s to 3.10 s). This reduction in latency brings the system down to a practical, interactive speed suitable for frontline barangay officials and victim assistance personnel.

Looking at what could be improved, the knowledge base is currently restricted to the 114-page Barangay VAW Desk Handbook, meaning these parameters will likely need recalibration when integrating broader multi-document corpora like R.A. 9262. Additionally, the prototype lacks conversational memory for multi-turn dialogue, relies heavily on plain text extraction that can struggle with complex tables or non-standard layouts, and depends on external GPU availability. Future iterations could explore hybrid dense-sparse retrieval (FAISS combined with BM25), semantic or heading-aware chunking to better preserve legal sections, adding short-term conversational buffering, and incorporating bilingual embedding models to handle mixed Tagalog-English queries.

Overall, this group experiment provided concrete, data-driven evidence that combining moderate chunk sizes with GPU acceleration delivers a precise, low-latency framework capable of supporting real-world legal and procedural guidance.
