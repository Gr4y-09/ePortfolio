---
title: Exercise WW-P2 (Data Cleaning)-reflection
---

### [🏠 Home](../index.md) | [💻 Projects](../projects.md) | [📚 ITC-C506 Coursework](../itc-c506.md) > **[Exercise WW-P2 (Data Cleaning)-reflection](./reflection/ExerciseWW-P2DataCleaning-reflection.md)**

---

The overall reflection on the data cleaning lab and the research paper illustrates the fundamental truth in machine learning: a model is only as good as the data it's trained on. The process of implementing the data cleaning pipeline gave a clear view of how raw consumer behaviour data, or 'noisy' data, can be processed into a reliable asset for predictive modelling.

The most transformative aspect of this exercise was the technical process of dealing with inconsistencies and outliers. In the lab, I observed that if the data set has more weight on one side, the k-Nearest Neighbors (k-NN) classifier would be more inclined to choose that side of the data set because that side has the larger numbers. Using the MinMaxScaler, I could normalize the features, so that each feature had an equal contribution to the distance calculation. The research paper shows that these tasks are not merely housekeeping, but have a significant impact on the “dependability” of the model, making its accuracy go from a basic to a professional level.

The concepts I introduced to actual government applications such as healthcare fraud detection or geotechnical audits did change my perspective on the "lazy learner" aspect of k-NN. In the healthcare industry, where the focus is on identifying "Fraudulent" from "Legitimate" billing, even a little bit of data noise can result in false accusations or missed theft. Likewise, at the urban geotechnical audit stage for construction permits, the bad sensor data can cause distance measurement error, potentially jeopardizing construction project safety. This is sobering to realize: the code I write in a Jupyter Notebook can have a life-changing impact on people if the data cleaning is not done with extreme care.

Finally, this part of the course work emphasized the ethical importance of transparency and human judgment. The problem with k-NN is that it does not explain the logic behind the choice of the neighbor, making it difficult to understand the algorithm, and so it's up to the developer to make sure that the data they use is perfect. If I were in government, I would take a "cautious" approach, and use these models as Decision Support Systems, but not as primary models. This process of ingesting raw data, cleaning and refining, has taught me that the iterative cycle of cleaning and refining is when the real engineering work occurs.
