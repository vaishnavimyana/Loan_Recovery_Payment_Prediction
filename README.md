# Loan Recovery: Payment Probability Prediction

## Project Overview
This project predicts whether a customer in loan recovery (30+ days past due) will make a payment in a given month. By identifying likely payers, recovery teams can prioritize high-probability accounts, making the collection process more efficient.

## Dataset
* **Source**: Internal loan recovery dataset[cite: 1].
* **Volume**: ~348,151 account-month records[cite: 1].
* **Timeline**: February 2023 – July 2023[cite: 1].
* **Target Variable**: `is_payer` (Derived from Pmt_amount)[cite: 1].

## Project Structure
* `AI_Project_Payment_Prediction.ipynb`: Main Python notebook with the end-to-end ML pipeline[cite: 1].
* `DataDictionary.docx`: Full documentation of the 27 data fields[cite: 1].
* `requirements.txt`: List of necessary Python libraries[cite: 1].
* `outputs/`: Folder containing visualizations and model performance charts[cite: 1].

## Key Findings
* **Class Imbalance**: Only ~9% of records resulted in a payment, requiring a stratified split and balanced weights during modeling[cite: 1].
* **Top Predictors**: `dpd_days`, `Principal_outstanding`, and `loan_age_days` were the strongest indicators of payment likelihood[cite: 1].
* **Model Performance**: The Balanced Random Forest Classifier achieved an **ROC-AUC of 0.79**[cite: 1].

## How to Run
1. Clone this repository.
2. Install dependencies: `pip install -r requirements.txt`.
3. Ensure the `Data_6Months.csv` is in the root folder.
4. Run `AI_Project_Payment_Prediction.ipynb`.

## Author
Vaishnavi | AI Engineer | 2026
