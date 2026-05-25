# Loan Default Risk with Business Cost Optimization

## Overview
Predict loan default likelihood and optimize decision thresholds based on cost-benefit analysis to minimize business losses.

## Objective
Build binary classification models and optimize the prediction threshold considering business costs of false positives and false negatives.

## Dataset
**The Dataset is available on kaggle**
- **Source:** Home Credit Default Risk Dataset
- **Samples:** ~70,000 loan applications (30% sample)
- **Features:** Demographics, income, credit amount, employment history, external scores
- **Target:** 1 - client with payment difficulties, 0 - all other cases

## Approach
1. **Data Loading:** Loaded application train data from Home Credit dataset
2. **Feature Selection:** Selected key features for modeling
3. **Feature Engineering:** Created financial ratios, age/employment conversions
4. **Data Preprocessing:** Handled missing values, encoded categoricals
5. **Model Building:** Trained Logistic Regression, Random Forest, and CatBoost
6. **Cost Definition:** Set FP cost = lost profit, FN cost = actual loss
7. **Threshold Optimization:** Found optimal thresholds for cost minimization
8. **Feature Importance:** Analyzed key risk factors

## Business Cost Model
- **False Positive Cost:** $10,000 (lost profit from rejecting good loan)
- **False Negative Cost:** $60,000 (loss from approving bad loan)
- **Cost Ratio:** 6:1 (false negatives are 6x more expensive)

## Files
- `Task4_Loan_Default_Risk.ipynb` - Main analysis notebook

## Requirements
```
pandas, numpy, matplotlib, seaborn, scikit-learn, catboost
```

## How to Run
1. Open the Jupyter notebook
2. Run all cells sequentially
3. Cost optimization curves and results will be displayed inline

## Key Insights
- External source scores (EXT_SOURCE_*) are strongest predictors
- Credit-to-income ratio is a critical risk factor
- Optimal threshold varies by model (typically 0.3-0.5)
- Business cost optimization can save millions compared to default threshold
