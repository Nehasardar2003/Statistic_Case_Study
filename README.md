# Credit Risk Analysis - Case Study

## 📌 Project Overview
This repository contains a comprehensive credit-risk analysis project that examines applicant data and historical loan behavior to identify key drivers of loan default. The analysis provides data-driven recommendations for credit policy improvements and hypothesis testing.

## 🎯 Objectives
- Identify strong predictors of loan default
- Conduct hypothesis testing on key demographic and financial factors
- Provide actionable credit policy recommendations
- Develop a tiered approval framework for risk-based lending

## 📊 Dataset Characteristics
### Applicant Data
- **Total Records:** 307,511 credit applications
- **Features:** 122 variables (106 numerical, 16 categorical)
- **Target Variable:** TARGET (1 = Default, 0 = Non-default)
- **Default Rate:** 8.07% (24,828 applications)

### Previous Loan Data
- **Total Records:** 1,670,214 credit risk previous loans
- **Features:** 37 variables (21 numerical, 16 categorical)

## 🔧 Data Processing
### Cleaning Strategy
1. **High Null Removal:** Dropped columns with >50% missing values (41 columns for applicants, 11 columns for loans)
2. **Feature Engineering:**
   - Converted DAYS_BIRTH to Age_years
   - Created YEARS_EMPLOYED from DAYS_EMPLOYED
   - Removed placeholder value 365243 (unemployed flag)
3. **Missing Value Treatment:**
   - Median imputation for numeric features
   - Zero imputation for credit bureau inquiries
   - Business logic imputation for AMT_GOODS_PRICE
   - "Unknown" category for categorical variables

## 📈 Key Insights
### Strong Predictors of Default
1. **EXT_SOURCE Variables:** Composite credit scores
2. **Days Employed:** Longer employment = lower default rates
3. **Credit-to-Income Ratio:** Primary financial health indicator
4. **Age:** Mature applicants show better repayment discipline
5. **Credit Bureau Inquiries:** Signal financial stress

### Demographic Risk Indicators
- **Gender:** Significant correlation with default rates (statistically confirmed)
- **Age:** Default rates vary across age brackets
- **Education Level:** Strong correlation with repayment behavior

## 🧪 Hypothesis Testing Results
### Test 1: Income Level Comparison
- **Method:** Two-sample t-test
- **Result:** Defaulters have significantly lower income (p = 0.0076)
- **Recommendation:** Income should account for 20-25% of credit scoring weight

### Test 2: Gender-Based Default Analysis
- **Method:** Chi-square test
- **Result:** Extremely strong association (p ≈ 0)
- **Recommendation:** Use gender as monitoring variable, not scoring variable

### Test 3: Education Level Correlation
- **Method:** Chi-square test
- **Result:** Extremely strong association (p ≈ 0)
- **Recommendation:** Education should account for 15-20% of credit score

## 💡 Business Recommendations
### Tiered Approval Framework
1. **Low-Risk Tier (Automatic Approval):**
   - EXT_SOURCE score > 0.7
   - Credit-to-Income < 40%
   - Employment > 5 years
   - Age 35-50 years

2. **Medium-Risk Tier (Enhanced Review):**
   - EXT_SOURCE 0.4-0.7
   - Credit-to-Income 40-60%
   - Employment 2-5 years

3. **High-Risk Tier (Manual Underwriting):**
   - EXT_SOURCE < 0.4
   - Credit-to-Income > 60%
   - Unemployment or recent job change

### Expected Outcomes
- **Reduce default rates** by 15-25%
- **Improve approval accuracy** while maintaining growth
- **Optimize capital allocation** through risk-based pricing
- **Enhance customer experience** with faster, fairer decisions

## 🛠️ Implementation
### Prerequisites
- Python 3.8+
- Pandas, NumPy, Scikit-learn
- Matplotlib, Seaborn for visualization
- Jupyter Notebook for analysis

## 📝 License
This project is for educational and research purposes. Please ensure compliance with data privacy regulations when implementing recommendations.

## 👥 Author
**Neha Manoj Sardar**  
PNR: 250840325045  
Project: Data-driven credit policy recommendations and hypothesis testing

## 📄 Documentation
For detailed analysis, methodology, and implementation guidelines, refer to the complete report in `reports/Analysis_report_Case_study_45.docx`
