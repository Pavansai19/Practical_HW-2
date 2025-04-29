Practical Homework 2 — Support Vector Machines (SVM)

📖 Overview

In this project, we explored Support Vector Machines (SVMs) to predict the likelihood of diabetes among adults using the 2022 NHIS dataset.
We handled real-world messy data, made modeling decisions based on critical thinking, and designed our workflow to mimic a real data science project — focusing not just on performance, but clarity and correctness.

⸻

 Methodology

1. Data Preparation
	•	Loaded the NHIS 2022 dataset.
	•	Replaced special codes (996, 997, 998, 999) with NA.
	•	Focused only on adults (Age ≥ 18) with valid diabetes history (Yes/No responses).
	•	Selected an initial set of health and lifestyle variables (e.g., Age, BMI, Sleep, Fruit intake, Soda consumption).

2. Initial Modeling
	•	Trained a basic Linear SVM to check feasibility.
	•	Observed significant class imbalance (“Yes” class was much smaller), impacting model performance.
	•	Realized that some variables had low impact on prediction.

3. Feature Importance
	•	Extracted feature importance from the basic Linear SVM.
	•	Selected top 6 most influential features (Age, BMI, Alcohol Days, Moderate Exercise, Pizza Intake, Soda Intake) to focus modeling efforts.

4. Improved Modeling
	•	Added class weights to give more importance to minority class (“Yes” for diabetes).
	•	Retrained:
	•	Linear SVM (weighted + reduced features)
	•	Radial SVM (weighted)
	•	Polynomial SVM (weighted)

5. Tuning and Evaluation
	•	Performed hyperparameter tuning on each model (cost, gamma, degree).
	•	Evaluated using Accuracy, Precision, Recall, and F1 Score.
	•	Created mini datasets (AGE vs BMICALC) to plot decision boundaries for clear visualization.

⸻
 Key Learnings
	•	Simply achieving high accuracy without considering class imbalance can be misleading.
	•	Feature selection based on importance simplified the models without major loss in performance.
	•	Radial SVM handled non-linear boundaries better than Linear SVM.
	•	Polynomial SVM struggled due to sensitivity to outliers and low generalization.
	•	Visualization of decision boundaries helped intuitively understand model behavior.

 Thought Process and Decisions
	•	Instead of blindly using all available features, we analyzed importance to reduce noise and complexity.
	•	Introduced class weights only after initial experiments showed clear imbalance issues.
	•	Focused on clean, interpretable plots (decision boundaries) using mini-datasets.
	•	Avoided overfitting by not making hyperparameter grids too complex.
	•	Took multiple iterations to fix errors — ensuring logical progression rather than shortcutting.

 References
	1.	Cortes, C., & Vapnik, V. (1995). Support-vector networks. Machine Learning.
	2.	American Diabetes Association. (2022). Standards of Medical Care in Diabetes—2022.
	3.	James, G., Witten, D., Hastie, T., & Tibshirani, R. (2021). An Introduction to Statistical Learning (2nd ed.). Springer.
	4.	ChatGPT (2025). Helped troubleshoot errors, debug data flow, and generate initial background illustrations. OpenAI ChatGPT.
	5.	U.S. National Health Interview Survey (NHIS) 2022. Dataset Access.
