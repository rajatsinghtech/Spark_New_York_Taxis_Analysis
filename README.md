> Written manually, without AI assistance.

# Spark_New_York_Taxis_Analysis

## What this does

Databricks notebook and write-up analysing the New York City taxicab dataset
with Apache Spark â€” answering business questions on trip volumes, fares,
tips, and duration bins, plus a linear-regression model predicting trip
fares. Same analysis as the
[portfolio post](https://rajatsingh.tech/portfolio/2023/01/15/data-processing-on-a-new-york-city-taxi-dataset-with-databricks/).

## Business process

Yellow/green taxi trip records (2019â€“2022) are cleaned, merged, and queried
with Spark SQL: trips per month, busiest weekday/hour, fare and tip
statistics, duration-bin economics (the 5â€“10 minute bin maximises driver
profit), then a fare-prediction model trained and scored (test RMSE â‰ˆ 7.08).

## Technical flow

Raw CSVs â†’ Azure Blob Storage â†’ mounted into Databricks â†’ cleaning
(filtering bad speeds, durations, passenger counts) â†’ new `time_duration`
and `speed` columns â†’ merged parquet â†’ Spark SQL answers â†’ linear
regression on trip distance, duration, and taxi type.

## Repository structure

- [`bde_at_2.html`](bde_at_2.html) â€” the exported Databricks notebook
- [`BDE-AT-2.pdf`](BDE-AT-2.pdf) â€” the PDF version of the analysis
