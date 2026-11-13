---
title: PT-F1 Reflection

---

### [🏠 Home](../index.md) | [💻 Projects](../projects.md) | [📚 ITC-C506 Coursework](../itc-c506.md) | [📚 ITC-C508 Coursework](../itc-c508.md) > **[PT-F1 Reflection](./itc-c508/reflection/PT-F1Reflection.md)**

---

This individual laboratory activity (PT-F1) focused on conducting a controlled chunking experiment to test how different chunk size and overlap configurations affect retrieval performance using a FAISS vector store and retrieval notebook. As part of our group's ongoing work around violence against women laws and local municipal guidance, I sourced my own dataset and set up test questions ranging from easy to difficult based on Republic Act No. 9710 (The Magna Carta of Women).

Working through the steps, I first annotated and commented the notebook cells to break down the technical pipeline clearly. Then, after selecting and verifying my dataset, I prepared three test questions with explicit ground-truth answers and source evidences: an easy factual question about the official short title (Section 1), an average interpretation question regarding international conventions like CEDAW (Section 2), and a difficult multi-passage question regarding congressional reporting mandates and effectiveness assessments (Section 40). Finally, I updated the baseline configuration from google/flan-t5-base to openai/gpt-oss-20b and implemented strict prompt guardrails ensuring the model answers exclusively using the provided document context with a precise fallback phrase.

Looking at what could be improved, performing this chunking experiment highlighted how sensitive vector retrieval is to document segmentation. Fixed-character chunking can sometimes split closely related statutory clauses across boundaries, which tests retrieval metrics like Precision@3, Recall@3, and MRR@3. While my selected configuration worked well for structured legal texts, relying purely on static character counts can occasionally disrupt context flow in dense legal provisions. Future experiments could explore semantic chunking to ensure that entire legal sections or articles remain intact within a single vector embedding.

Overall, this exercise provided a great hands-on look at how data preprocessing and parameter tuning directly impact the retrieval quality of a RAG pipeline before any generation takes place.
