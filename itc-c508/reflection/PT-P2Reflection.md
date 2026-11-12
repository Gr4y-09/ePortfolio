---
title: PT-P1 Reflection

---

### [🏠 Home](../index.md) | [💻 Projects](../projects.md) | [📚 ITC-C506 Coursework](../itc-c506.md) | [📚 ITC-C508 Coursework](../itc-c508.md) > **[PT-P2 Reflection](./itc-c508/reflection/PT-P2Reflection.md)**

---

This second activity focused on taking our text intent classifier out of the no-code environment and building a custom feedforward neural network using Python and Keras. Moving from a simple 15-sample baseline to a scaled 600-row dataset allowed us to test how different hyperparameter settings like learning rates, optimizers, and dropout regularization affect model training and performance.

Working through the various experimental runs really showed how delicate neural network training can be. When we tested uncalibrated settings, like an overly high learning rate in EXP-03 or a non-adaptive SGD optimizer in EXP-05B, the models either completely diverged or suffered from severe gradient stagnation and underfitting. On the flip side, pairing the expanded 600-row dataset with an adaptive Adam optimizer, a low learning rate, and moderate dropout in EXP-05 allowed the training and validation losses to drop smoothly together, achieving a perfect validation accuracy and a 1.0000 Weighted F1-score.

Looking at what could be improved, while our optimal model (EXP-05) hit incredible metrics on paper, laboratory datasets still don't capture the full chaos of real-world user text. Even with 600 rows, synthetic or cleaned datasets can sometimes mask subtle data drift, domain-specific slang shifts, or complex multi-intent messages that users actually type into support chatboxes. Additionally, relying heavily on a simple feedforward architecture with global average pooling means the model misses out on word order and sequential grammar nuances that a recurrent network or transformer might catch. Future improvements could involve testing more advanced architectures (like LSTMs or small transformers), incorporating real-time user feedback loops to continuously retrain the model, and testing how well it handles messy, multi-sentence inputs with mixed sentiment.

Comparing this code-based approach to our earlier no-code project (PT-P1) made the trade-offs really clear. No-code tools are great for getting a quick baseline up and running, but they act as a black box that hides important controls. Writing the code manually in Keras gives you complete transparency and precision over every part of the pipeline allowing you to fix overfitting and capacity bottlenecks though it definitely requires more careful tuning to avoid breaking the model.

Overall, this experiment was a great way to bridge the gap between high-level theory and actual implementation. It proved that getting a neural network to perform reliably isn't just about throwing architecture at a problem; it requires a careful balance of data volume, proper regularization, and fine-tuned optimization.
