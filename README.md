# Credit-Card-Fraud-Detection
**Project Overview**
This project focuses on detecting fraudulent credit card transactions using machine learning algorithms. Originally developed as my university capstone project, I found the process highly engaging and decided to extend it after gaining a deeper understanding of machine learning. This curiosity led me to explore ways to further improve the model’s performance and refine the detection techniques.

## **Key Objectives**

. Analyze credit card transaction data to identify patterns indicative of fraud.

. Build and evaluate machine learning models to detect fraudulent transactions.

. Improve accuracy and minimize false positives, thus reducing financial risk.


## **Data Source**

The dataset used for this project can be found here: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

## **Project Workflow**


### **1. Data Preprocessing**

To address the class imbalance, where fraudulent transactions represented a small fraction of the dataset, I applied techniques such as SMOTE (Synthetic Minority Over-sampling Technique) to balance the data. Additionally, feature scaling was performed to standardize the dataset, ensuring uniformity across features and enhancing the model’s performance. The dataset was then split into training (80%) and testing (20%) sets to facilitate proper model evaluation and prevent overfitting.


### **2. Exploratory Data Analysis (EDA)**

.Visualized transaction data using histograms, boxplots, and correlation heatmaps.


.Identified key features strongly associated with fraud (e.g., certain anonymized variables like V4 and V12).


### **3. Model Development**
Multiple machine learning algorithms were applied and compared, including:

.Logistic Regression


.Random Forest Classifier


.Support Vector Machines (SVM)



### **4. Model Evaluation**
. Accuracy: The proportion of correctly identified transactions.

. Precision: Focused on minimizing false positives.

. Recall (Sensitivity): Maximized the detection of true fraud cases.

. F1 Score: A balance of precision and recall.

### **5. Hyperparameter Tuning**
The KNN model, trained on the oversampled data, delivered the best performance. I then fine-tuned its hyperparameters to further optimize accuracy and balance between precision and recall, improving its ability to detect fraudulent transactions.



## **Results**
![image](https://github.com/user-attachments/assets/0878a207-977f-4298-b0f8-115792425145)


