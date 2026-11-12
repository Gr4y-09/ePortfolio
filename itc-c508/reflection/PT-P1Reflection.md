---
title: PT-P1 Reflection

---

### [🏠 Home](../index.md) | [💻 Projects](../projects.md) | [📚 ITC-C506 Coursework](../itc-c506.md) > **[PT-P1 Reflection](./itc-c508/reflection/PT-P1Reflection.md** | [📚 ITC-C508 Coursework](../itc-c508.md)

---
This laboratory activity about training a text classification model to route customer feedback really opened my eyes to how machine learning handles language compared to writing regular computer code. Using the Machine Learning for Kids tool, we built a simple neural network to sort customer messages into three groups: positive praise, negative complaints, and urgent support.

Working through the project made me realize how important the training data is. When we only used three examples per class, the model’s guesses were all over the place and had really low confidence. Expanding it to ten examples per class helped the model make much better decisions and stopped it from just guessing based on a single keyword like "great".

What could be better, though, is that the model still had major blind spots. Because our dataset was pretty small only 30 examples total it completely choked on sarcastic comments and weird words it hadn't seen before. For example, a sarcastic complaint completely confused it, and random phrases just forced it to spit out a low-confidence guess instead of saying it didn't understand. If I were to do this again, I’d definitely want to add a lot more data, include tricky sarcastic examples in the training set, and set up a confidence cutoff so the system knows when to ask for a human helper.

Looking at how the system works behind the scenes, it makes total sense why we use machine learning instead of a bunch of hardcoded if/else statements for text. Trying to write rules for every single way a customer could phrase a complaint would take forever and get super messy because human language is so unpredictable. Watching how the text gets broken down into tokens, turned into vectors, and passed through the neural network to get probabilities showed me how neat the automated feature extraction process actually is.

Overall, this activity showed me that while AI models are super cool and way better at handling natural language than old-school rule-based scripts, they are only as good as the data you feed them. Building something reliable in the real world takes a lot more than just a quick dataset—you really have to plan for edge cases, messy phrasing, and unexpected inputs.
