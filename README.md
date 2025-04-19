# parameter_optimization

🧠 Project Overview
This project explores the use of Support Vector Machines (SVMs) for binary classification using the Bank Marketing Dataset from the UCI repository. The main objective is to compare different SVM kernels and tune their hyperparameters to find the best-performing model. The final model’s learning behavior is then analyzed using a learning curve.

🧪 Methodology
1. Dataset Acquisition
The dataset was fetched using the ucimlrepo library (UCI ML Repo ID: 222).

The features (X) and target labels (y) were separated.

The data was preprocessed by:

Handling categorical variables using pd.get_dummies.

Standardizing numerical features using StandardScaler.

2. Sample Generation
The dataset was split into 10 different train-test splits using train_test_split with different random_state values to simulate various real-world scenarios.

3. SVM Kernel Comparison
For each sample, four SVM kernels were tested:

linear

poly

rbf

sigmoid

For each kernel, random hyperparameters (C and gamma) were sampled within:

C ∈ [0.1, 10]

gamma ∈ [0.001, 1]

The fitness function was defined as the classification accuracy on the test set.

The best-performing kernel and hyperparameters were recorded for each sample.

📊 Result Table

Sample	Best Accuracy	Best Kernel	Best C	Best Gamma
1	0.9023	rbf	5.12	0.0342
2	0.8997	poly	6.78	0.0081
...	...	...	...	...
10	0.9051	rbf	4.67	0.0127

![image](https://github.com/user-attachments/assets/63b39305-ffb9-443e-96e5-8f0ecd3e1faf)

🔎 Note: The values shown here are illustrative — refer to your result DataFrame for actual outputs.

This table summarizes the best accuracy, along with the corresponding kernel, C, and gamma values found for each of the 10 samples. It highlights how different kernel functions and hyperparameter choices can influence performance.

📈 Learning Curve (Best Model)
The best-performing model from the result table was selected and used to plot a learning curve. This curve shows how the model's accuracy changes as the size of the training data increases.

![image](https://github.com/user-attachments/assets/cf18b45b-249c-4afd-8dbc-7776f07473c2)

Key Insights:
Training Accuracy Curve: Indicates how well the model fits the training data. A high value shows good fit.

Validation Accuracy Curve: Shows the model’s generalization to unseen data. A stable, rising curve suggests reliable learning behavior.

Gap between the two: A small gap indicates low overfitting, while a large gap can suggest overfitting or underfitting depending on accuracy levels.

📌 Conclusion
The SVM with RBF kernel generally performed the best across different data splits.

Hyperparameters C and gamma play a critical role in model performance.

The learning curve demonstrates that the model benefits from more training data, but also shows where performance plateaus.

