Practical Homework 2 — Support Vector Machines (SVM)

 Overview

In this project, we explored Support Vector Machines (SVMs) to predict the likelihood of diabetes among adults using the 2022 NHIS dataset. We focused on clean modeling practices: handling real-world messy data, identifying the most predictive features, and tuning models to balance performance and fairness. Our workflow was structured to mirror how data science is done in real-world projects.

⸻

Methodology

1. Data Preparation
	•	Loaded the NHIS 2022 dataset.
	•	Replaced special codes (996, 997, 998, 999) with NA.
	•	Filtered for adults (Age ≥ 18) with valid diabetes responses (Yes/No).
	•	Selected initial health and lifestyle variables: Age, BMI, Sleep, Exercise, Diet, Alcohol, etc.

2. Initial Modeling
	•	Trained a basic Linear SVM on full data.
	•	Identified heavy class imbalance (very few “Yes” cases).
	•	Saw that several features had little to no predictive value.

3. Feature Selection
	•	Used linear SVM-based feature importance to select top 6 variables:
	•	Age, BMI, Alcohol Days, Moderate Exercise, Pizza Intake, Soda Intake.

4. Improved Modeling
	•	Added class weights to give more influence to the minority (“Yes”) class.
	•	Re-trained 3 weighted SVM models:
	•	Linear SVM
	•	Radial SVM
	•	Polynomial SVM

5. Mini Dataset + Tuning
	•	Created a balanced mini dataset (500 Yes, 500 No).
	•	Applied hyperparameter tuning (cost, degree) on the polynomial model.
	•	Tuned Polynomial SVM on this 1000-sample dataset gave:
	•	Accuracy: 66.3%
	•	Recall: 87.3%
	•	Precision: 61.5%
	•	F1 Score: 72.3%
	•	Confusion matrix showed strong performance on positive detection (recall) with moderate false positives.

⸻

Key Learnings
	•	High accuracy can be misleading in imbalanced datasets — recall and F1-score matter more.
	•	Reducing features based on importance simplified models without losing much performance.
	•	Untuned polynomial SVMs performed poorly despite high accuracy due to zero recall.
	•	The tuned polynomial SVM on a mini dataset was the most balanced and effective.
	•	Confusion matrix heatmaps and performance plots helped visualize model strengths and trade-offs.

⸻

Thought Process & Decisions
	•	Prioritized interpretability over complexity in both modeling and tuning.
	•	Used class weights only after observing how imbalance affected early results.
	•	Focused on recall due to the real-world importance of identifying diabetic individuals.
	•	Balanced simplicity and performance by tuning on a smaller, well-structured dataset.
	•	Iterated based on feedback, improving our final results and presentation clarity.

⸻

References
	1.	Cortes, C., & Vapnik, V. (1995). Support-vector networks. Machine Learning.
	2.	American Diabetes Association (2022). Standards of Medical Care in Diabetes—2022.
	3.	James, G., Witten, D., Hastie, T., & Tibshirani, R. (2021). An Introduction to Statistical Learning (2nd ed.).
	4.	NHIS Dataset — U.S. National Health Interview Survey, 2022.
	5.	OpenAI ChatGPT (2025) — Assisted with debugging, tuning strategy, and data visualization design.
