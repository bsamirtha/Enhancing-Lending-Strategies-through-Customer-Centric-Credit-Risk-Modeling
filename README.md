# Enhancing-Lending-Strategies-through-Customer-Centric-Credit-Risk-Modeling

## Introduction

Customer-centric credit risk modeling plays a crucial role in modern financial institutions by enabling precise assessment of individual borrower risk. By leveraging data-driven insights, these models help lenders evaluate a customer's likelihood of default, allowing for tailored loan terms, quicker credit decisions, and optimized risk management. 

This approach not only safeguards institutions from potential losses but also enhances customer satisfaction through personalized services. As regulatory requirements tighten and competition intensifies, customer-focused credit risk modeling offers a strategic advantage, balancing risk mitigation with profitability, and promoting responsible lending practices.

## Objective

The objective of this project is to **predict loan defaults** based on customer data using machine learning models. By analyzing key features such as credit history, income levels, and previous financial behavior, the model will help in identifying high-risk customers and minimizing potential loan defaults.

## Dataset Description

The dataset consists of 9 columns, each providing specific details about customers and their loan profiles:

- **Customer ID**: A unique identifier for each customer.
- **Loan Status**: `0` indicates the loan is under non-default, while `1` indicates the loan is under default.
- **Loan Amount**: The amount of money sanctioned as a loan to the customer.
- **Interest Rate**: The interest rate applied to the loan, which varies based on several factors. Some entries contain missing values, which must be handled appropriately before building any predictive models.
- **Grade**: Likely represents the customer’s credit grade, influencing loan approval and terms.
- **Employment Length**: The number of years the customer has been employed or their work experience, which could affect loan risk evaluation.
- **Home Ownership**: Specifies whether the customer owns a home or rents, potentially playing a role in risk assessment for loan approval.
- **Annual Income**: Provides information about the customer’s income, impacting their loan eligibility and repayment ability.
- **Age**: Reflects the customer's age, which, alongside income, might influence their eligibility and the perceived risk of default.

### Data Considerations

Addressing the missing values, especially in key columns like **Interest Rate**, is crucial to ensure the accuracy and reliability of the predictive models. Proper data cleaning and preprocessing steps will be necessary to handle missing values and any other potential data quality issues.

# Key Learnings from Credit Risk Modeling

1. **Handling Missing Values**: 
   - Identified and addressed missing values in critical columns like `int_rate` and `emp_length`. The approach of median imputation was selected for these columns to maintain data integrity and reduce bias caused by outliers.

2. **Class Imbalance**: 
   - Noted the significant class imbalance in the `loan_status` variable, where only 11% of loans were defaults. Implementing Synthetic Minority Over-sampling Technique (SMOTE) helped create synthetic examples of the minority class, ensuring that the model could recognize patterns in loan defaults more effectively.

3. **Outlier Treatment**: 
   - Extreme outliers, especially in the `annual_income` column (e.g., $6M), were addressed through log transformation, which stabilized variance and improved the model's predictive performance. Additionally, erroneous values in the `age` column (e.g., ages over 100) were either corrected or removed to refine the dataset.

4. **Encoding Categorical Variables**: 
   - Emphasized the importance of converting categorical features like `home_ownership` and `grade` into numeric form using techniques such as one-hot encoding. This transformation is crucial for effective model training, as many machine learning algorithms require numerical input.

5. **Feature Selection and Model Performance**: 
   - The final model, after selecting the top 8 important features, achieved a high accuracy score of **90.47%**. The balanced performance metrics (precision, recall, and F1-score) indicate that the model can predict both defaults and non-defaults effectively, suggesting that feature selection can simplify the model without sacrificing performance.
