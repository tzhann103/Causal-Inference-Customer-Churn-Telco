# Causal-Inference-Customer-Churn-Telco

This project estimates the **causal effect of contract type** on customer churn using modern causal inference methods applied to observational telecom data.

---

## 1. Research Objective

The primary objective of this project is to estimate the causal effect of contract type on customer churn. Specifically, we seek to determine how being on a long-term contract (one-year or two-year) affects a customer’s probability of churning, relative to a month-to-month contract.

The target estimand is the Average Treatment Effect (ATE).

---

## 2. Methodology

Because contract choice is endogenous and driven by customer characteristics such as tenure, service usage, and billing behavior, simple comparisons of churn rates are not causally interpretable. To address this selection bias, we employ causal inference methods to approximate a randomized experiment using observational data.

### Data & Setup
- **Dataset:** Telco Customer Churn (2019)  
- **Treatment:** Enrollment in a long-term contract (one-year or two-year)  
- **Outcome:** Customer churn (binary indicator)

### Key Methods
- **Inverse Probability Weighting (IPW)** to reweight observations and balance covariates across treatment groups  
- **Doubly Robust (DR) Estimation**, combining IPW with outcome regression for improved robustness  

### Diagnostic Checks
Model validity and robustness were assessed through:
- Propensity score overlap diagnostics 
- Covariate balance checks using standardized mean differences (SMDs)
- Propensity score trimming to improve common support and reduce reliance on extrapolation  

---

## 3. Key Findings

The results indicate that long-term contracts have a large and statistically significant causal effect on reducing customer churn:

- **IPW Estimate (Full Sample)**  
  Being on a long-term contract reduces the probability of churn by 21.0 percentage points  
  *(ATE = −0.2102)*

- **Doubly Robust (DR) Estimate**  
  A more conservative estimate shows a 16.5 percentage point reduction in churn  
  *(ATE = −0.165)*

- **Robustness Check (Trimmed IPW)**  
  After restricting the analysis to customers with strong covariate overlap, the estimated reduction in churn remains statistically significant at approximately 11.6 percentage points

---

## 4. Conclusion

These findings confirm that the substantially lower churn rates observed among long-term contract customers are causal in nature, and not solely the result of customer self-selection. Contract structure itself plays a meaningful role in improving customer retention, highlighting its importance as a strategic lever in subscription-based businesses.

---

## Repository Contents

- `Causal_Impact_of_Contract_Type_on_Customer_Churn.ipynb` — Full analysis and code  
- `report/` — Final project report  
- `slides/` — A concise presentation summarizing the business motivation, causal framework, and key results

---

## Notes

This project was completed as part of **DSO 599: Causal Inference with Machine Learning for Business Analytics** at the University of Southern California.

