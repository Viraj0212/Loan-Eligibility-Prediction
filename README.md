# Loan-Eligibility-Prediction-Ml
Model Comparison for Loan Prediction
This notebook explores and compares multiple classification models to predict loan approval based on applicant details. We compare the performance of Random Forest Classifiers and Support Vector Machines (SVM) using different configurations.

✅ Random Forest Classifiers
Model	       Estimators	     Accuracy	                     Comments
Model 1	      500	              0.811        	Best recall for class 'Y' (0.97), but weaker on class 'N'
Model 2	      100	              0.793        	Slightly lower accuracy, more false positives
Model 3	      1000	            0.802        	Comparable to Model 1, but increased computation time with no significant gain

📌 Best Choice: RandomForestClassifier(n_estimators=500)

✅ Support Vector Machines (SVM)
Model            	Kernel	        Accuracy	                Comments
Model 4          	Linear	          0.829	      Highest overall accuracy; perfect recall for class 'Y'
Model 5	           RBF	            0.685      	Predicts only class 'Y'; fails entirely on class 'N'
Model 6	          Sigmoid	          0.685      	Slightly better than RBF for 'N', but still weak overall

📌 Best Choice: SVC(kernel='linear')

📊 Confusion Matrix Insights
All models demonstrate a strong bias toward predicting 'Y' (Loan Approved).
A high number of false positives (misclassified 'N') suggests the presence of class imbalance in the dataset.

🔧Recommendations for Improvement
Address Class Imbalance: Use balanced class weights in classifiers or apply oversampling techniques such as SMOTE to ensure better representation of minority classes.
Apply Cross-Validation: Utilize cross-validation techniques like k-fold or grid search to enhance model reliability and parameter tuning.
Feature Scaling: Normalize input features, especially for algorithms like SVM, to improve convergence and overall model performance.


✅ Conclusion
Best Random Forest Model: n_estimators=500
Best SVM Model: kernel='linear'
Future work should focus on handling class imbalance, tuning with cross-validation, and feature scaling for optimal SVM performance.
