# Credit Card Fraud Financial Loss Prediction — V4

Run:
```bash
python -m pip install -r requirements.txt
python -m streamlit run app.py
```

## Important amount range
The source dataset contains transaction amounts from **$1.00 to $28,948.90**. The app intentionally blocks values outside this range. A value such as $2,998,000 is far outside the training distribution, so a prediction for it would not be scientifically supported.

## Modeling
The final regression model estimates expected financial exposure. During training, an independent fraud-risk model was used to create an expected-loss target: transaction amount × estimated fraud probability. The required Linear Regression and Random Forest Regressor models were then trained to estimate that continuous value.

The dataset does not contain a separately confirmed bank-loss field, so the app describes the output as estimated financial loss/exposure, not confirmed loss.
