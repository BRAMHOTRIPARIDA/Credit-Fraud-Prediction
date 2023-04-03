# Credit Fraud Prediction
---------------------------------------------------
Fraud is a problem for any bank and can take many forms ranging from stealing single credit card to using large number of stolen credit card numbers on the network, or a huge compromise of credit card numbers which are stolen from merchants via tools like credit card skimming devices.

Objective : Build a predictive model based on historical transactions to determine whether a given transaction will be fraudulent or not.

Dataset - https://github.com/CapitalOneRecruiting/DS 


Methodology :
---------------------------------------------------
1) Data Summarization, Analysis and Visualization
---------------------------------------------------
• Exploration

• Correlation

2) Data preprocessing : 
---------------------------------------------------
• Handling missing values

• Label encoding

3) Modeling algorithm : Random Forest
---------------------------------------------------
Since the dataset is huge, it can be handled using Random Forest.
Random Forest is based on the bagging algorithm and it builds many trees on subsets of the data and combines the output of all the trees. 
This reduces overfitting and also reduces variance and thus improves accuracy.
Also it works well with both categorical and continuous variables and is robust to outliers and can handle them automatically. 
The top 10 features from this initial model is used for model enhancement.

4) Model Enhancement :
---------------------------------------------------
Recall : The recall is a measure of the model correctly identifying True Positives. 
Thus for all the actual fraud transactions, recall tells us how many we correctly identified as being a fraud transaction.
Recall = True Positives / (True Positives + False Negatives)
Since the Recall is very low, upsampling the minority class ('isFraud' = 'True') to improve recall.

5) Final model performance results :
---------------------------------------------------
The accuracy is (99.7%) and recall is 100% on test data. So we can infer that the RandomForest model generalizes well. This leads to inferring that data overfitting might be less.

Future Enhancements :
---------------------------------------------------
• Binning numerical fields - Binning the continuous features in the data can help improve the model performance on test data as it helps introduce non-linearity.

• Using Stratified k fold Cross Validation - The upsampling of the minority class can increase the likelihood of overfitting because it makes exact copies of the minority class samples. Cross validation reduces overfitting and 5-fold Stratified k-fold Cross-Validation can be used to train RandomForest model. It provides train and test index to split data in train-test data sets. The stratified k fold cross-validation if used for classification problems with class imblance maintains the same class ratio throughout the K folds same as the ratio in the original dataset. This ensures that the cross-validation output result is a close approximation of the generalization error in the data. At each k-fold cross-validation split, only the training set is oversampled which can be achieved using a machine learning pipeline and this prevents data or information leakage from train to test data. This ensures that the test data is not oversampled.

• Using Repeated Stratified k fold Cross Validation - This can improve model performance on unseen data and give a robust model.

• Hyper-parameter tuning for Random Forest and cross-validation - To enhance model efficiency.

• Deep diving into the causal of different interesting patterns of reversed and multiswipe transactions and deriving features based on causal-effect relationship between attributes in the data.
