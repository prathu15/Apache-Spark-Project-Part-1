


## Project Overview

This project demonstrates an end-to-end data engineering pipeline built using **Apache Spark**.
The use case is from the **finance domain**, where the objective is to clean, transform, and process loan-related data to support **risk analysis** and **loan approval decisions**.

Multiple datasets are used such as customer details, loans, repayments, and defaulters.
The processed and standardized data can be used further by analytics teams to calculate **credit risk scores** and generate insights.



## Data Sources

1. "Customers (Borrowers)""
   `member_id, emp_title, emp_length, home_ownership, annual_inc, addr_state, zip_code, country, grade, sub_grade, verification_status, ...`

2. **Loans**
   `loan_id, member_id, loan_amnt, funded_amnt, term, int_rate, installment, issue_d, loan_status, purpose, title`

3. "Loan Repayments"
   `loan_id, total_rec_prncp, total_rec_int, total_rec_late_fee, total_pymnt, last_pymnt_amnt, last_pymnt_d, next_pymnt_d`

4. "Loan Defaulters"
   `member_id, delinq_2yrs, delinq_amnt, pub_rec, pub_rec_bankruptcies, inq_last_6mths, total_rec_late_fee, ...`

---

## Data Engineering Workflow

1. "Data Ingestion"

   * Load raw CSV data into Spark DataFrames.
   * Store data in HDFS or cloud storage.

2. "Data Cleaning & Transformation"

   * Handle duplicates, nulls, and missing values.
   * Rename inconsistent columns (e.g., `annual_inc → annual_income`).
   * Standardize formats (e.g., convert `emp_length` to integer).
   * Replace invalid values (`addr_state` set to `NA` if not valid).
   * Add metadata column such as `ingestion_date`.

3. "Data Processing"

   * Generate unique customer IDs using SHA2 hashing.
   * Apply Spark transformations (`withColumn`, `when`, `concat_ws`, `cast`).
   * Create aggregated views for analytics such as repayment trends and default ratios.

4. "Data Validation & Testing"

   * Validate schema, null checks, and business rules.
   * (Unit testing using PyTest was part of course material but not implemented here).

5. "Deployment"

   * Code packaged for execution in Dev → Stage → Prod environments.
   * Parameterized Spark jobs for scalability.

---

## Business Use Case

* Lending institutions need to decide whether to approve or reject a loan.
* Approving a loan for a high-risk borrower leads to financial losses.
* Rejecting a loan for a low-risk borrower leads to business loss.
* This system provides **cleaned and enriched data** to analytics teams for calculating **credit risk scores** and optimizing loan approvals.

---

## Technologies Used

* Apache Spark (PySpark) – data processing and transformations
* HDFS – data storage
* Python – scripting
* CI/CD tools – deployment pipeline
* Cloud / On-Prem infrastructure – scalable cluster setup

---

## Dataset Scale

* Dataset size: \~1.7 GB
* Records: 2+ million
* Columns: 118 attributes across datasets
* Cluster size: Configurable, scales with workload

---

## Key Outcomes

* Clean, reliable, and standardized datasets for analytics.
* Automated ETL pipeline for financial data.
* Scalable infrastructure for large datasets.
* Risk score generation to support loan approval decisions.


