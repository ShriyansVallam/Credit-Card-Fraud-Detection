# Credit-Card-Fraud-Detection
**Project Overview**
This project focuses on detecting fraudulent credit card transactions using machine learning algorithms. Originally developed as my university capstone project, I found the process highly engaging and decided to extend it after gaining a deeper understanding of machine learning. This curiosity led me to explore ways to further improve the model’s performance and refine the detection techniques.


## **Dataset**

The dataset used for this project contains 284,807 rows and the features have been anoymized to ensure privacy. The data set can be found here: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

## **Data Preprocessing and EDA**

The biggest challenge with this dataset was the massive imbalance between fradulent transactions compared to non-fradulent transactions 
![image](https://github.com/user-attachments/assets/77f03889-fc7b-46e2-aa5f-32385393c2b0)

 As seen in the image above, only 0.2% of the dataset consists of actual fraud. It is crucial to address class imbalance as training a model on inbalanced data leads to the model being highly biased to the majority class. To demonstrate this, I initially trained a Logistic Regression Model on the imbalanced data.

![image](https://github.com/user-attachments/assets/aef96b5e-7989-440a-8af3-c7b2725d1e26)

 The model achieved an accuracy of 0.9991, which might seem impressive at first glance. However, accuracy is not a reliable metric in the case of imbalanced datasets, as it can be misleading when the majority class dominates. The recall for the minority class was only 0.58, which means 42% of the actual fradulent transactions were missed. This is a critical issue for fraud detection, as failing to identify fraud could result in significant financial losses.

To address this issue, I utlized both undersampling and oversampling. I also used SMOTE, however it performed significantly worse:
* **Oversampling:** involves creating more instances of the minority class by replicating existing samples or generating synthetic samples that resemble the minority class instances. This aims to increase the representation of the minority class in the dataset

![image](https://github.com/user-attachments/assets/5d71a966-9e20-48fa-9600-a2996e14bb25)


* **Undersampling:** Involves reducing the number of instances in the majority class by randomly removing samples. This is done to balance the proportion of classes in the dataset

![image](https://github.com/user-attachments/assets/6e110428-a012-4fda-a267-751c6b9a6c89)

## **Main Findings**
Two algorithms were used to build the fraud detection model:

* **Logistic Regression: A baseline** classifier to understand the relationship between features and the probability of fraudulent transactions.
* **K-Nearest Neighbors (KNN):** A distance-based algorithm that classifies transactions based on the similarity to neighboring data points.

Both models were trained on the undersampled and oversampled datasets and each model was evaluated using the following metrics:
* **Confusion Matrix:** To visualize the number of true positives, true negatives, false positives, and false negatives for each model.
* **Classification Report:** To evaluate precision, recall, and F1-score, which are critical in assessing the performance of fraud detection.
* **Matthews Correlation Coefficient (MCC):** To provide a balanced measure of the model's performance, particularly useful for imbalanced datasets.

The image below shows the results for all the different cases: 

![image](https://github.com/user-attachments/assets/4a2f4a08-3d6d-4c6c-a25e-b61e9d2927bd)

As we can see the KNN model trained on oversampled data has both good precision and recall, as a result **hyperparameter** **tuning** was performed on the model to enhance it's performance as seen below

![image](https://github.com/user-attachments/assets/42fbef5e-9814-4fa1-8290-ff9aece706d7)

**Final Model Evaluation**

![image](https://github.com/user-attachments/assets/b257f860-b765-426f-bac5-4cbcfff3386f)

* The model achieved a recall of 0.88 for the minority class (fraud), meaning it successfully identified 88% of fraudulent transactions
* The precision for the minority class was 0.61, indicating that there is still room for improvement in reducing false positives
* The F1-score for the fraud class was 0.72, which represents a good balance between precision and recall
* The MCC was 0.7337, which indicates a strong correlation between the predicted and actual classes, providing a more reliable assessment of model performance in imbalanced scenarios
