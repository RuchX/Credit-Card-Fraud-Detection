# Credit Card Fraud Detection - Machine Learning Project

📊 Project Overview

An end-to-end machine learning project that detects credit card fraud using real-world transaction data. This project demonstrates data analysis, feature engineering, model development, and business intelligence visualization.

**Dataset:** Kaggle Credit Card Fraud Detection (284,807 transactions)  
**Models Used:** Random Forest Classifier, Logistic Regression  
**Dashboard:** Power BI with interactive visualizations

🎯 Problem Statement

Credit card fraud is a critical issue in the financial services industry. With only 0.17% of transactions being fraudulent, we need sophisticated ML models that can:
- Detect fraud with high recall (catch frauds without missing them)
- Minimize false positives (avoid flagging legitimate transactions)
- Provide interpretable results for business decision-making

📈 Key Results

| Metric | Random Forest | Logistic Regression |
|--------|---------------|-------------------|
| Accuracy | 99.56% | 98.76% |
| Precision | 82.34% | 65.21% |
| Recall | 87.01% | 72.34% |
| F1-Score | 0.8463 | 0.6857 |
| ROC-AUC | 0.9887 | 0.9654 |

**Winner:** Random Forest (captures non-linear fraud patterns)

🔍 Data Analysis Insights

## Fraud Distribution
- **Total Transactions:** 284,807
- **Fraudulent Transactions:** 492 (0.17%)
- **Legitimate Transactions:** 284,315 (99.83%)
- **Class Imbalance:** 578:1 ratio

## Key Findings
- **Fraud by Time:** Afternoon has highest fraud count (45 incidents)
- **Fraud by Amount:** 
  - Low (<$50): 82 frauds (66.7%)
  - Medium ($50-$250): 40 frauds (25.3%)
  - High (>$250): 26 frauds (8.0%)
- **High-Value Transactions:** Show higher fraud risk
- **Temporal Pattern:** Fraud occurs consistently across all hours

## 🛠️ Methodology

## 1. Data Exploration & Cleaning
- Loaded 284,807 credit card transactions with 31 features
- Checked for missing values and outliers
- Analyzed fraud distribution and class imbalance
- Applied IQR method for outlier handling

## 2. Feature Engineering
Created 5 new features based on financial domain knowledge:
- **Hour:** Extracted from transaction timestamp (0-23)
- **TimePeriod:** Morning/Afternoon/Evening/Night categorization
- **LogAmount:** Log-transformed transaction amount
- **AmountCategory:** Categorized into Low/Medium/High based on distribution
- **Transaction_Velocity:** Sum of last 5 transaction amounts

## 3. Data Preprocessing
- Standardized all features using StandardScaler
- Applied SMOTE to handle severe class imbalance
- Stratified train-test split (70:30)
- Balanced training set (50% fraud, 50% legitimate)

## 4. Model Development
**Random Forest Classifier:**
- 100 decision trees
- Max depth: 15
- Min samples split: 10
- Non-linear pattern detection

**Logistic Regression:**
- Baseline linear model
- Max iterations: 1000
- Regularization included

## 5. Model Evaluation
- Confusion matrix analysis
- Precision-Recall trade-off evaluation
- ROC-AUC comparison
- Feature importance analysis

📊 Power BI Dashboard

**Interactive dashboard with 8+ visualizations:**
1. **KPI Cards:** Total frauds (148), Legitimate count (85,295), Fraud rate (0.17%), Average fraud amount ($130.49)
2. **Fraud Activity by Hour:** Temporal patterns across 24 hours
3. **Fraud by Time Period:** Morning/Afternoon/Evening/Night breakdown
4. **Transaction Amount vs Fraud Risk:** Scatter plot showing amount-fraud relationship
5. **Fraud by Amount Category:** Low/Medium/High distribution
6. **Model Performance Comparison:** Random Forest vs Logistic Regression
7. **High-Risk Transactions:** Detailed table of flagged transactions
8. **Model Accuracy Gauge:** 99.91% Random Forest accuracy

**Features:**
- Dark professional theme
- Color-coded fraud indicators (Red=Fraud, Green=Legitimate)
- Interactive filters (Amount Category, Hour, Time Period)
- Real-time insights panel


Credit-Card-Fraud-Detection/
├── README.md                          # Project documentation
├── requirements.txt                   # Python dependencies
│
├── notebooks/
│   └── Fraud_Detection_Analysis.ipynb # Complete Python analysis
│
├── data/
│   ├── fraud_predictions_for_powerbi_FIXED__1_.csv    # Model predictions (85,443 rows)
│   ├── feature_importance__1_.csv                     # Feature importance scores
│   └── dataset_summary__1_.csv                        # Summary statistics
│
├── dashboard/
│   ├── Fraud_Detection_Dashboard.pbix # Power BI dashboard
│   └── dashboard_screenshot.png       # Dashboard preview
│
└── docs/
    └── PROJECT_REPORT.md              # Detailed technical report


🚀 How to Use

## Running the Notebook
1. Open `notebooks/Fraud_Detection_Analysis.ipynb` in Google Colab
2. Install dependencies: `pip install -r requirements.txt`
3. Run all cells sequentially
4. Notebook generates CSV files for Power BI

## Viewing the Dashboard
1. Download `dashboard/Fraud_Detection_Dashboard.pbix`
2. Open with Microsoft Power BI Desktop
3. Interact with visualizations using filters
4. Explore fraud patterns by amount, hour, time period

## Reproducing Results
- Dataset: Kaggle Credit Card Fraud Detection
- Python 3.8+
- See `requirements.txt` for library versions
- Expected runtime: 5-10 minutes

📊 Technologies Used

**Data Analysis & ML:**
- Python 3.8+
- Pandas, NumPy (data manipulation)
- Scikit-learn (machine learning)
- Imbalanced-learn (SMOTE)
- Matplotlib, Seaborn (visualization)

**Business Intelligence:**
- Microsoft Power BI (interactive dashboard)

**Version Control:**
- Git, GitHub

💡 Key Learnings

1. **Class Imbalance Handling:** SMOTE effectively balances severe imbalance (578:1 ratio)
2. **Non-linear Patterns:** Random Forest outperforms linear models (87% vs 72% recall)
3. **Domain Knowledge:** Feature engineering based on financial domain improves model
4. **Business Metrics:** Recall prioritized over accuracy for fraud detection
5. **Temporal Patterns:** Fraud shows distinct time-of-day patterns (afternoon peak)

🎓 Domain Knowledge Applied

This project leverages **Financial Services & Cards Practice training** from Capgemini:
- Banking operations and payment lifecycle understanding
- Cards processing knowledge
- Fraud pattern recognition
- Risk assessment frameworks
- Velocity-based fraud detection (rapid consecutive transactions)

📈 Results Summary

- **Fraud Detection Rate:** 87.01% (catches 87% of fraud)
- **False Positive Rate:** 17.66% (2 legitimate flagged per 10 frauds)
- **Average Fraud Amount Detected:** $130.49
- **Model Accuracy:** 99.56% on imbalanced test set
- **Feature Importance:** V14 (20.5%), V4 (11.6%) are top fraud indicators

🔮 Future Enhancements

1. **Real-time Prediction API:** Deploy model as REST API
2. **Advanced Anomaly Detection:** Isolation Forest, One-Class SVM
3. **Time-Series Analysis:** LSTM for sequential transaction analysis
4. **Explainability:** SHAP values for model interpretability
5. **A/B Testing:** Compare model performance in production
6. **Automated Retraining:** Pipeline for continuous model updates

📧 Contact & Links

**Portfolio Project by:** Ruchita Patre  
**GitHub:** [github.com/ruchita-patre](https://github.com/ruchita-patre)  
**LinkedIn:** [linkedin.com/in/ruchita-patre](https://linkedin.com/in/ruchita-patre)  
**Email:** [patreruchita675@gmail.com]

🙏 Acknowledgments

- **Dataset Source:** Kaggle - Credit Card Fraud Detection
- **Training:** Capgemini Technology Services - Financial Services & Cards Practice
- **Mentor:** Mansi Goel (YouTube) - Data Analytics guidance

**Last Updated:** August 2026  
**Project Status:** Complete ✅
