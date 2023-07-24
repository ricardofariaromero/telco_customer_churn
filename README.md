# Telecommunications Customer Churn

For this project, it was used a database with information of a set of customers from a telecommunications company. The objective is to create a model that predicts if a client will continue as a customer in the following months. The DB contains 21 features and 7043 records.

![alt text](https://github.com/ricardofariaromero/telco_customer_churn/blob/main/images/telecommunications.jpeg)


## Variables and EDA

The variables to analyzed will be the following:

    - customerID: unique ID for the customer.
    - gender: whether the client is male or female.
    - SeniorCitizen: indicates if the client is senior or not.
    - Partner: if the client has a partner.
    - Dependents: if the clients has people who depend on them.
    - tenure: how many months they have as a customer
    - PhoneService: if the client has phone service contracted.
    - MultipleLines: if the client has multiple lines contracted.
    - InternetService: if the client has internet service contracted.
    - OnlineSecurity: if the client has online security service contracted.
    - OnlineBackup: if the client has online backup service contracted.
    - DeviceProtection: if the client has device protection service contracted.
    - TechSupport: if the client has tech support service contracted.
    - StreamingTV: if the client has streaming TV service contracted.
    - StreamingMovies: if the client has streaming movies service contracted.
    - Contract: type of contract of the client (month to month, yearly, etc.)
    - PaperlessBilling: whether the client receives its billing on paper or electronically.
    - PaymentMethod: which payment method the client uses.
    - MonthlyCharges: how much does the client pays.
    - TotalCharges: how much payment has the client acumulated.
    - Churn: if the client is active or not.

First, we identified how many clients stayed and how many left last month:

![alt text](https://github.com/ricardofariaromero/telco_customer_churn/blob/main/images/churn.png)

After analyzing the impact of each variable on churn data we estimated that the following has no influence on customer permanence or are redundant with other variables:

    - customerID
    - gender:
    - MultipleLines:
    - StreaminTV:
    - StreamingMovies:
    - TotalCharges


## Python Libraries and algorithm

The following libraries were used during this project:

    - Pandas
    - Seaborn
    - Matplotlib
    - Scikit-learn (Random Forest Classifier, KNN, Logistic Regression and XGBoost algorithms)

## Analysis and results

First we tried to implement a simple Random Forest Classifier, with the following results:

Confusion Matrix
![alt text](https://github.com/ricardofariaromero/telco_customer_churn/blob/main/images/matrix_not.png)

ROC
![alt text](https://github.com/ricardofariaromero/telco_customer_churn/blob/main/images/roc_not.png)

We compared these results with other algorithms such as KNN, Logistic Regression and XGBoost, not getting better results. It was then implemented hyperparameters and cross validaton on RFC but also, increasing the class with less ocurrence by using a RandomOverSampler. We got the following hyperparameters values:

    - 'n_estimators': 175
    - 'min_samples_split': 2
    - 'min_samples_leaf': 1 
    - 'max_features': 'auto' 
    - 'max_depth': None 
    - 'bootstrap': False

And the following metrics:

    - Precision Score: 0.8670309653916212
    - Accuracy Score: 0.8962962962962963
    - Recall Score: 0.9327237099934683
    - F1 Score: 0.8986784140969164
    - AUC for our classifier is: 0.9653181973230908

Confusion Matrix
![alt text](https://github.com/ricardofariaromero/telco_customer_churn/blob/main/images/confusion_matrix.png)

ROC
![alt text](https://github.com/ricardofariaromero/telco_customer_churn/blob/main/images/roc.png)
        
## Credits

All code and development performed by [Ricardo Faría](https://www.linkedin.com/in/ricardo-e-faria-romero/?locale=en_US) 
