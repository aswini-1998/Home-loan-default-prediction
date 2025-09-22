# **Home Loan Default Prediction**

This machine learning project aims to predict whether a home loan applicant will default on their loan. Using a variety of data sources related to applicants' financial history, we build a classification model to assess credit risk. This is a binary classification problem where the model predicts if a client will repay their loan (0) or default (1).

---

## **Project Workflow** ⚙️

The entire workflow is contained within the `HomeLoan.ipynb` Jupyter notebook. The process is as follows:

1.  **Data Loading**: All datasets are loaded into pandas DataFrames.
2.  **Feature Engineering & Merging**: Data from the supplementary files are aggregated for each unique loan application (`SK_ID_CURR`). These aggregated features are then merged into the main application dataset to create a single, comprehensive DataFrame.
3.  **Data Preprocessing**: Before modeling, rows with missing values are removed to create a clean dataset for training.
4.  **Modeling**: A **Random Forest Classifier** is used for prediction. The modeling process is streamlined using a Scikit-learn `Pipeline` which first scales the data with `StandardScaler` and then feeds it to the classifier.
5.  **Evaluation**: The model's performance is evaluated using a **5-fold cross-validation** strategy. The final output is the average accuracy score across all 5 folds, which gives a reliable estimate of the model's predictive power on unseen data.

---

## **Datasets** 🗂️

The project utilizes seven datasets to build a complete financial profile for each applicant:

* **`application_train.csv`**: The main dataset containing the primary loan application information and the target variable (whether the client defaulted).
* **`bureau.csv`**: Contains information about applicants' previous credits from other financial institutions reported to the credit bureau.
* **`bureau_balance.csv`**: Provides monthly data on the status of the credits listed in `bureau.csv`.
* **`previous_application.csv`**: Includes data on previous loan applications made by the applicants at our institution.
* **`POS_CASH_balance.csv`**: Contains monthly data about previous point-of-sale or cash loans.
* **`credit_card_balance.csv`**: Provides monthly balance data for credit cards held by the applicants.
* **`installments_payments.csv`**: Includes payment history for previous loans.

---

## **Results** 📈

The model's performance is measured by its accuracy in predicting loan defaults. The notebook will output the accuracy score for each of the 5 cross-validation folds and the final average accuracy. This provides a robust measure of the model's ability to generalize to new, unseen data.
