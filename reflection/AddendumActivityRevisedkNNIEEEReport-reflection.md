---
title: Addendum Activity: Revised kNN IEEE Report-revision

---

### [🏠 Home](../index.md) | [💻 Projects](../projects.md) | [📚 ITC-C506 Coursework](../itc-c506.md) > **[Addendum Activity: Revised kNN IEEE Report-revision](./reflection/AddendumActivityRevisedkNNIEEEReport-reflection.md)**

---

Doing this research and the related lab work has really helped me have a new perspective on data. Seeing a clean dataset in a classroom is one thing, but when it comes to comparing the performance of a k-Nearest Neighbors (k-NN) Classifier with and without preprocessing, you can see how much “invisible” work it takes to make a successful project. The Iris data set was used and I personally experienced the model's errors, even though it was 96.67% accurate, it still made a mistake and classified a Versicolor as a Virginica 3.33% of the time. This is a small gap, but a good example of the fact that k-NN doesn't work well when feature boundaries are not clearly defined or are overlapping, and I'm going to learn a great lesson in my senior year.

I was most fascinated by the relationship between my technical notebook and the applications in government and engineering. Our lab exercises are more meaningful when we see that researchers such as Galupino and Dungca have also used the same Euclidean distance method to estimate soil density for construction permits in Valenzuela City. That's a little scary to think that if I got that wrong in that situation, the building could collapse, and in my notebook, it was just a mislabeled flower. It really highlights the fact that k (n_neighbors) is not just a number that's adjusted for a grade, it's a very important parameter to choose for a model to be stable enough for public safety.

It was the ethical aspect of this research that really came as a 'aha' moment for me. I didn't consider k-NN as a "functional black box" until I read about the lack of algorithmic transparency and that it doesn't explain why it selects a certain neighbour as the best match. That would be a huge public service failure if we applied an unvalidated model to allocate disaster relief and rejected a burned farm due to "noise" in the data. This is why it is important to not only use the machine, but to use it as a Decision Support System, not a replacement for human judgment as future IT professionals.

Last but not least, the technical details of the audit, such as using MinMaxScaler and train_test_split, made me realize that the “iterative cycle” is the most crucial step of the machine learning pipeline. It can be atmospheric correction for satellite imagery, or simply splitting data to prevent overfitting, the point is to fulfill ethical requirements in a technical manner. I am taking this project with a lot more appreciation for the "data sanitization" process and a "cautious" attitude towards deployment of these algorithms in the future. 
