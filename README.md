# E-Commerce Customer Segmentation with RFM Analysis & K-Means Clustering

## Project Overview

This project focuses on performing customer segmentation for an e-commerce business using a data-driven approach. By leveraging Recency, Frequency, and Monetary (RFM) analysis in conjunction with K-Means clustering, the goal is to identify distinct customer groups to enable targeted marketing and improve customer relationship management.

## Research Question

How can we segment our customer base into distinct, actionable groups based on their historical purchasing behavior (Recency, Frequency, Monetary Value) to identify our most valuable customers and tailor retention and marketing strategies accordingly?

## Dataset

The analysis uses transactional data from a UK-based online retailer, contained in the `e-commerce-data.csv` file. Key attributes of the dataset include:

* `InvoiceNo`: Transaction identifier (cancellations indicated by 'C' prefix).
* `StockCode`: Product identifier.
* `Description`: Product name.
* `Quantity`: Number of items per transaction (negative for returns).
* `InvoiceDate`: Date and time of transaction.
* `UnitPrice`: Price per unit in Pounds Sterling (£).
* `CustomerID`: Unique customer identifier (some missing values).
* `Country`: Customer's country of residence.

The dataset originally contains 541,909 rows and 8 columns.

## Methodology

1.  **Data Preprocessing:** Handled missing `CustomerID` values, cleaned `Quantity` and `UnitPrice` for valid transactions, and derived `Total Price`.
2.  **RFM Calculation:** Calculated Recency (days since last purchase), Frequency (total number of purchases), and Monetary (total spending) values for each customer.
3.  **Data Scaling:** Applied appropriate scaling to RFM variables to ensure fair contribution to the clustering algorithm.
4.  **K-Means Clustering:**
    * Determined the optimal number of clusters (`k`) using the Elbow Method and Silhouette Score.
    * Applied K-Means clustering to segment customers based on their RFM scores.
5.  **Cluster Profiling:** Analyzed the characteristics of each identified customer segment based on their average RFM values to create distinct customer personas.

## Key Findings

* **Successful Segmentation:** Successfully segmented 4084 unique customers into 3 distinct and meaningful clusters.
* **Model Performance:** The K-Means clustering model achieved a silhouette score of 0.408, indicating a decent quality of the generated clusters, where clusters are well-separated.
* **Actionable Personas:** Identified 3 unique customer personas with clear and actionable characteristics. These personas can be used to:
    * Develop customized marketing campaigns.
    * Improve customer retention strategies.
    * Personalize product recommendations and offers.

## Tools and Libraries Used

* **Programming Language:** Python
* **Data Manipulation:** `pandas`, `numpy`
* **Data Visualization:** `matplotlib`, `seaborn`, `plotly`
* **Machine Learning:** `scikit-learn` (for `KMeans`, `silhouette_score`, `PCA`)
