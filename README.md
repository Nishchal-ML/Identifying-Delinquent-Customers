📂 Give Me Some Credit – Predicting Financial Distress
This project solves the popular "Give Me Some Credit" problem from Kaggle, where the goal is to predict whether a person will experience financial distress in the next two years, based on their financial behavior and history.

📌 Problem Statement
Predict the probability that a person will default on a loan (label SeriousDlqin2yrs = 1) using historical financial attributes.

This is a binary classification problem with a highly imbalanced dataset, which makes it more realistic and challenging for credit risk modeling.

🧠 What This Notebook Covers
This project follows a complete machine learning pipeline:

Step	Description
1️⃣ Data Overview	File structure, basic samples, dataset shape
2️⃣ Missing Value Handling	Detected and imputed MonthlyIncome using age-group medians  
3️⃣ EDA	Distribution plots, outlier inspection, and feature-target relationships
4️⃣ Feature Engineering	Age binning, log transformations, IQR-based clipping, target-aware encoding  
5️⃣ Encoding & Scaling	Used OneHotEncoder and StandardScaler within a pipeline
6️⃣ Logistic Regression	Baseline model with/without class imbalance correction
7️⃣ Random Forest	Tree-based model with class_weight='balanced'
8️⃣ XGBoost	Tuned with scale_pos_weight to handle imbalance
9️⃣ Threshold Tuning	Compared results at multiple thresholds (0.3, 0.4, 0.5)
🔟 Final Submission	Probabilities generated and formatted as per Kaggle requirement

📊 Key Techniques Used
✅ Missing value imputation (by group median)

✅ IQR-based outlier handling

✅ Binning + custom recoding of categorical variables

✅ Feature scaling and encoding with ColumnTransformer

✅ Class imbalance handling: class_weight, scale_pos_weight, and threshold tuning

✅ Evaluation: precision, recall, F1-score

✅ Pipeline modeling using Scikit-learn

🧪 Threshold Tuning Impact on Random FOrest Classifier
Metric	    Threshold 0.3	 Threshold 0.5	Threshold 0.7	        Use Cases
Precision	      0.1424	     0.2202	         0.3632	      For Flaging risking Profiles
Recall	        0.8889	     0.7225	         0.5153	      Balanced System
F1 Score	      0.2454	     0.3376	         0.4261	      Auto Rejecting High Risk Profiles

This shows how tuning probability thresholds can align the model with business needs (e.g., reducing false negatives).


🏆 Model Comparison Summary
Metric	    Logistic (raw)     Logistic Regression (balanced)	  Random Forest Classifier (0.5 Threshold)	  XGBoost Classifier
Precision	     0.00                0.1891	                              0.2202	                                0.2153
Recall	       0.00                0.7084	                              0.7225	                                0.7572
F1 Score	     0.00                0.2985	                              0.3376	                                0.3353

✅ XGBoost gave the best recall while maintaining reasonable precision.

📁 Repository Structure
sql
Copy
Edit
├── give-me-some-credit-dataset - Project.ipynb   # Final notebook with end-to-end workflow
├── submission.csv                      # Kaggle submission file
├── README.md                           
📦 Deploy with Streamlit: Upload a CSV and get default probability

📚 Dataset Source
Kaggle – Give Me Some Credit

👨‍💻 Author
Nishchal Pandey
Aspiring Data Scientist | BI Analyst | ML Projects Enthusiast
