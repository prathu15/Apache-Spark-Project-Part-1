

# Apache Spark Project – Lending Club Data Engineering (Part 1)

## Overview

This project focuses on building a data engineering pipeline using "PySpark" for the "Lending Club dataset". The dataset contains information about customers, loans, repayments, and defaulters. The goal is to clean, process, and prepare the data for downstream analytics and risk modeling.



## Key Objectives

1. "Data Cleaning & Standardization"

   * Handle duplicates, null values, missing data, and datatype mismatches.
   * Rename inconsistent columns for clarity.
   * Add ingestion timestamps.

2. "Data Transformation"

   * Convert categorical and string-based columns into usable formats.
   * Replace invalid or missing state codes with "NA".
   * Convert employment length into integer values and impute nulls with averages.

3. "Domain Use Case"

   * Lending Club (Peer-to-Peer lending platform).
   * Problem: Predict whether a loan should be approved or declined.
   * Goal: Minimize risk for investors while avoiding business loss by wrongly rejecting good customers.

4. "Agile Methodology"

   * Work delivered in "sprints".
   * Stories broken into tasks → unit testing, cleaning steps, ingestion jobs.
   * CICD pipelines used for deployment.

---

## Dataset

* "customers\_data" → borrower details
* "loans\_data" → loan details
* "loan\_repayments" → repayments history
* "loan\_defaulters" → delinquency, bankruptcies, and public records



## Cleaning Steps

* Customers Data:

  * Remove duplicates.
  * Drop rows with null `annual_income`.
  * Standardize `state` codes.
* Loans Data:

  * Validate loan purpose against lookup list.
* Repayments:

  * Fix invalid date formats.
* Defaulters:

  * Normalize delinquency counts, bankruptcy records.

---

## Tools & Technologies

* "PySpark" (ETL & transformations)
* "HDFS" (storage)
* "Agile" (Scrum methodology)
* "CI/CD pipelines" for deployment
* "Pytest" for unit testing


