# Bank-Loan-Report-Analysis-Using-SQL
Project Overview
This project involves analyzing bank loan data using SQL to extract key insights. The dataset contains details on loan applications, funded amounts, interest rates, debt-to-income (DTI) ratios, and loan statuses. Various SQL queries were written to generate meaningful KPIs, such as monthly trends, good vs. bad loan percentages, and overall loan performance.

Key Features
1. Loan Application Analysis
Total Loan Applications: Count of all loan applications.
Month-to-Date (MTD) Applications: Applications submitted in the current month.
Previous Month-to-Date (PMTD) Applications: Applications submitted in the previous month.
2. Financial Metrics
Total Funded Amount: The sum of all loan amounts.
MTD & PMTD Funded Amounts: Loan amounts funded in the current and previous months.
Total Amount Received: The sum of all loan repayments collected.
MTD & PMTD Amount Received: Repayments collected in the current and previous months.
3. Interest Rate & DTI Analysis
Average Interest Rate: The mean interest rate of all loans.
MTD & PMTD Interest Rate: Monthly trend of average interest rates.
Average DTI Ratio: The mean debt-to-income ratio of borrowers.
MTD & PMTD DTI Ratio: Monthly trend of DTI ratios.
4. Loan Performance Evaluation
Good Loan Percentage: Percentage of loans that are ‘Fully Paid’ or ‘Current.’
Bad Loan Percentage: Percentage of loans that are ‘Charged Off.’
Good vs. Bad Loan Applications & Funded Amounts: Comparison of loan statuses.
5. Loan Status Breakdown
Loan count, total amount received, funded amounts, and interest rates grouped by loan status.
MTD and PMTD breakdown for loan statuses.
6. Loan Distribution Analysis
Loan trends by Month, State, Employment Length, Loan Term, Purpose, and Home Ownership.
Filter-based analysis to drill down into specific loan characteristics (e.g., filtering by grade).
Technologies Used
SQL (PostgreSQL / MySQL)
Data Analysis
Query Optimization
Data Filtering & Aggregation
SQL Queries
The project contains well-structured SQL queries that analyze loan performance, trends, and distributions. Some key queries include:

sql
Copy
Edit
-- Total Loan Applications
SELECT COUNT(id) AS Total_Applications FROM bank_loan_data;

-- Good Loan Percentage
SELECT 
    (COUNT(CASE WHEN loan_status = 'Fully Paid' OR loan_status = 'Current' THEN id END) * 100.0) / 
    COUNT(id) AS Good_Loan_Percentage
FROM bank_loan_data;

-- Monthly Loan Analysis
SELECT 
    EXTRACT(MONTH FROM issue_date) AS Month_Number, 
    COUNT(id) AS Total_Loan_Applications,
    SUM(loan_amount) AS Total_Funded_Amount
FROM bank_loan_data
GROUP BY EXTRACT(MONTH FROM issue_date)
ORDER BY Month_Number;
A full list of queries is available in the project repository.

Conclusion
This SQL project provides a comprehensive analysis of bank loan data, offering insights into loan distribution, repayment trends, and borrower behavior. The queries help stakeholders make data-driven decisions regarding loan approvals and risk assessment.
This SQL project provides a comprehensive analysis of bank loan data, offering insights into loan distribution, repayment trends, and borrower behavior. The queries help stakeholders make data-driven decisions regarding loan approvals and risk assessment.


