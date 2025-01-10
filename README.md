Introduction
This project aims to predict heart disease risk using both distributed and non-distributed machine learning approaches. The study compares performance metrics, scalability, and speed-up for Decision Tree and Random Forest algorithms implemented using Python's scikit-learn and PySpark’s MLlib.

Machine Learning Details
Type of Learning: Binary Classification
Algorithms Used:
Non-Distributed: Decision Tree, Random Forest (scikit-learn).
Distributed: Decision Tree, Random Forest (PySpark’s MLlib).
Parallelization Approach:
PySpark’s MLlib distributed framework leverages Spark’s in-memory distributed computing for training and evaluating the models.
Dataset Overview
Description:
The dataset contains health-related indicators (e.g., BMI, smoking status, mental health) and a target variable HeartDisease indicating whether the individual was diagnosed with heart disease.
Source: Kaggle Dataset
Dataset Details

Columns:
HeartDisease (Target Variable): Yes/No
BMI: Body Mass Index
Smoking: Smoking status
AlcoholDrinking: Alcohol consumption
PhysicalHealth: Poor physical health days in the last month
MentalHealth: Poor mental health days in the last month
DiffWalking: Difficulty walking
Other features: Sex, AgeCategory, PhysicalActivity, GenHealth, SleepTime.
Features Selected:
Predictors: BMI, Smoking, AlcoholDrinking, PhysicalHealth, MentalHealth, DiffWalking, Sex, AgeCategory, PhysicalActivity, GenHealth, SleepTime
Target: HeartDisease
Data Volume:
Original Dataset: 565,817 rows (~237 MB).
After Balancing: 584,787 rows (~270 MB).
Results
Non-Distributed Implementation

Metrics

Decision Tree:
Accuracy: 91.48%
Precision: 93.24%
Recall: 85.12%
F1 Score: 89.00%
Random Forest:
Accuracy: 93.78%
Precision: 94.45%
Recall: 89.32%
F1 Score: 91.81%
Confusion Matrices

Decision Tree:
0.0: Correct = 88,123 | Incorrect = 11,432
1.0: Correct = 19,874 | Incorrect = 5,412
Random Forest:
0.0: Correct = 89,221 | Incorrect = 10,334
1.0: Correct = 20,567 | Incorrect = 4,719
Distributed Implementation

Metrics

Decision Tree:
Accuracy: 73.70%
Precision: 73.74%
Recall: 73.69%
F1 Score: 73.68%
Random Forest:
Accuracy: 74.19%
Precision: 75.05%
Recall: 74.19%
F1 Score: 73.98%
Confusion Matrices

Decision Tree:
0.0: Correct = 62,828 | Incorrect = 25,044
1.0: Correct = 66,511 | Incorrect = 21,122
Random Forest:
0.0: Correct = 57,137 | Incorrect = 30,735
1.0: Correct = 73,077 | Incorrect = 14,556
Measured Metrics
Speed-Up:
Decision Tree: ~2.33x
Random Forest: ~1.48x
Size-Up:
Double Dataset: Random Forest Execution Time: ~240 seconds (2.0x baseline).
Triple Dataset: Random Forest Execution Time: ~360 seconds (3.0x baseline).
Scale-Up:
Low Parallelism: 122.27 seconds.
High Parallelism: 122.54 seconds.
Scale-Up Factor: ~1.0 (indicates good scalability).
Visualizations
The project includes:

Accuracy and F1 Score comparisons between distributed and non-distributed implementations.
Confusion matrices for both implementations.
Speed-up and scale-up charts visualizing performance improvements.
How to Use This Project
Prerequisites:
Python 3.7+
Libraries: scikit-learn, pyspark, pandas, numpy, matplotlib.
Execution:
Run non-distributed implementations locally using scikit-learn.
Execute distributed implementations on a Spark cluster.
Dataset Preparation:
Download and preprocess the Kaggle dataset as described.
Results Analysis:
Review performance metrics and visualizations for insights.
