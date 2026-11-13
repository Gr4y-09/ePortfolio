---
title: PT-M1 Reflection

---

### [🏠 Home](../../index.md) | [💻 Projects](../../projects.md) | [📚 ITC-C506 Coursework](../../itc-c506.md) | [📚 ITC-C508 Coursework](../../itc-c508.md) > **[PT-M1 Reflection](./itc-c508/reflection/PT-M1Reflection.md)**

---

This third project shifted our focus toward building a retrieval-augmented generation (RAG) pipeline designed to handle Philippine legal statutes, specifically Act No. 3815 (The Revised Penal Code) and Republic Act No. 3019 (Anti-Graft and Corrupt Practices Act). Because general-purpose language models often hallucinate legal provisions, the goal of this system was to ground the model's responses in verifiable, external database chunks while suppressing ungrounded output.

The system architecture relies on several well-connected components. Raw text files are loaded via LangChain's DirectoryLoader and split into 500-character segments with a 50-character overlap using a recursive character text splitter to keep statutory clauses intact. These chunks are converted into 384-dimensional vectors using Hugging Face's all-MiniLM-L6-v2 model and indexed in ChromaDB. For retrieval, the system uses Maximum Marginal Relevance (MMR) search fetching an initial candidate pool of 10 chunks and re-ranking them to select the 6 most diverse and relevant chunks before passing them to the Groq llama-3.1-8b-instant inference engine with a temperature of 0.0.

Testing across three benchmark scenarios in-domain summaries, out-of-domain queries, and cross-document synthesis proved that the setup works exceptionally well. When tested with an out-of-domain query like asking for a spaghetti carbonara recipe, the vector retriever pulled the closest legal text due to nearest-neighbor matching, but strict prompt guardrails and zero-temperature sampling forced the model to return the exact fallback phrase ("I cannot answer based on the provided domain data.") instead of making something up. By contrast, raising the temperature to 1.0 and removing the guardrails caused the model to completely ignore missing context and hallucinate a full recipe using its internal memory.

Looking at what could be improved, while our RAG pipeline successfully eliminated hallucinations for completely unrelated queries, it still relies heavily on the quality of vector similarity search. If a user asks a legal question using vocabulary that differs significantly from the exact statutory wording or if a query spans multiple complex articles that get split awkwardly across chunk boundaries the MMR retriever might pull suboptimal chunks, limiting the model's synthesis accuracy. Additionally, a static chunk size of 500 characters can occasionally isolate a penalty clause from its governing definition if they fall across a boundary. Future iterations could benefit from implementing semantic chunking based on legal article structures, adding a hybrid search combining keyword (BM25) and vector retrieval, and incorporating an automated evaluation step to score faithfulness and answer relevance.

Overall, this project provided a fantastic look at how combining vector databases, precise chunking strategies, and strict system prompt guardrails can turn an unconstrained generative model into a secure, audit-ready domain assistant.
