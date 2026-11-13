---
title: PT-F1 Reflection

---

### [🏠 Home](../../index.md) | [💻 Projects](../../projects.md) | [📚 ITC-C506 Coursework](../../itc-c506.md) | [📚 ITC-C508 Coursework](../../itc-c508.md) > **[PT-F1 Reflection](./itc-c508/reflection/PT-F1Reflection.md)**

---

This reflection paper covers our collaborative work on the final group experimentation and report for our Retrieval-Augmented Generation (RAG) chatbot project focusing on Violence Against Women and Girls (VAWG) in the Philippines, utilizing the Barangay VAW Desk Handbook (2023) and Republic Act No. 9710 (The Magna Carta of Women).

My Contributions & Experimental Role
As the third member listed in our group contributions, my primary responsibilities centered around the quantitative evaluation, technical parameter testing, and performance benchmarking of our RAG pipeline. Specifically, my work covered:

- RAG Experimentation & Parameter Selection: Following up on our past individual experiments, I selected two of my previous chunking configurations, while another group member contributed their configurations. After merging our datasets into a single combined knowledge base, we tested these carried-over parameters to establish our group experimental matrix.
- Parameter Configuration & Chatbot Testing: Testing and evaluating multiple chunk size and overlap configurations (such as 800/80, 500/50, 1500/300, and 300/60) to determine how text segmentation impacts document retrieval.
- Retrieval & Benchmark Evaluation: Assessing retrieval accuracy across our standardized 12-question benchmark suite (divided evenly across Easy, Average, and Difficult tiers) using metrics like Precision@3, Recall@3, and Mean Reciprocal Rank at 3 (MRR@3).
- CPU and GPU Performance Benchmarking: Executing comparative runtime tests across Google Colab CPU and NVIDIA T4 GPU environments.
- Time Logging & Execution Tracking: Implementing and debugging Python time-logging codelines within our Jupyter Notebook (.ipynb) to accurately capture indexing time, average response time, and total execution time across all test runs.
- Experimentation Logging & Performance Comparison: Consolidating data into structured logs to evaluate the computational speedups and trade-offs between CPU and GPU hardware.

Key Insights from the Experiment
Through our systematic testing, we observed distinct performance trade-offs across the pipeline. While larger chunk configurations like 1500/300 achieved higher mathematical retrieval scores on certain metrics (such as a Precision@3 of 0.5833 and MRR@3 of 0.7778), qualitative analysis of the retrieved passages revealed that the 800/80 configuration provided much more cohesive, relevant, and contextually complete answers for practical barangay workflows.

On the hardware side, benchmarking demonstrated that GPU execution drastically accelerated intensive computational steps—such as dropping indexing time on the 1500/300 setup from over a minute down to 5.48 seconds—though overall response times varied based on the generation load. Ultimately, we adopted the 800/80 configuration with a Top-K of 3 paired with GPU execution as our final recommended setup, balancing retrieval relevance with processing efficiency.

Overall, this experiment provided a deep technical understanding of how data preprocessing parameters and hardware acceleration directly influence the reliability and speed of domain-specific RAG applications.
