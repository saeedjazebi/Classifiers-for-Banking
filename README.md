# Classifiers-for-Banking
My goal is to compare the performance of the classifiers, namely K Nearest Neighbor, Logistic Regression, Decision Trees, and Support Vector Machines. I will utilize a dataset related to marketing bank products over the telephone. Our dataset comes from the UCI Machine Learning repository link (https://archive.ics.uci.edu/dataset/222/bank+marketing). The classification goal is to predict if the client will subscribe (yes/no) a term deposit (variable y).
The link to the Jupyter Notebook: https://github.com/saeedjazebi/Classifiers-for-Banking/blob/main/Classifiers_for_Banks.ipynb
Imported the required libraries. 
Loaded the full dataset.
Started reading the data and undertanding the data fields and what each one of them mean.
There are both categorical features as well as numerical features.
Looked at the data information. There is no nulls in the data. The data is clean!
The "duration" attribute highly affects the output target (e.g., if duration=0 then y='no'). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model. Therefore, i dropped this column from the data set.
The correlation matrix was developed with respect to numerical data. The durtaion is highly corrolated with "campaign" data. Therefore, might be a good idea to make sure that we use this feature more effectively.
The histogram plots and pairplots are used to figure out the relationships between data features. 
The numerical columns are then transformed with StandardScaler and the categorical features converted to numbers using TergetEnoder.
Next, the data is broken down to test and training data sets.
5 models are selected: Logistic regression, SVM, KNN, Decision Tree, and Random Forest. The models are developed for the dataset and compared against each other based on traning error, test error, and training time. 
The SVM model seems to be outperforming with respect to accuracy. However, the training time is highest. Logistic Regression however, is good for both accuracy and training time.
Looking at the Confusion Matrix, it was obsereved that True Negatives are predicted well, however, True Positives, which are more important in this case are not predicted correctly.
Also, it was revealed that the dataset is very unbalanced. Hence, training and testing data sets were balanced for fine tuning. 
Next, the SVM, Random Forest, and KNN were tuned for better performance, using GridSearchCV.
The three models are now performing with almost similar perfomance. The random forest however, has lowe traning time and highest test accuracy.
The recall is the best performance measure for this application. 
