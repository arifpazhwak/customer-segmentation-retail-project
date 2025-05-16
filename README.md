# Unveiling Customer Personas: A K-Means Clustering Approach for Strategic Retail Marketing

<p align="left">
  <img src="https://img.shields.io/badge/Python-3.x-blue.svg?style=flat-square" alt="Python 3.x"/>
  <img src="https://img.shields.io/badge/Pandas-Used-green.svg?style=flat-square" alt="Pandas Used"/>
  <img src="https://img.shields.io/badge/NumPy-Used-green.svg?style=flat-square" alt="NumPy Used"/>
  <img src="https://img.shields.io/badge/Scikit--learn-Used-orange.svg?style=flat-square" alt="Scikit-learn Used"/>
  <img src="https://img.shields.io/badge/Plotly-Used-purple.svg?style=flat-square" alt="Plotly Used"/>
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square" alt="License: MIT"/>
</p>

---

## Project Overview

This project explores the application of unsupervised machine learning, specifically K-Means clustering, to perform customer segmentation for a retail company. It was undertaken as a capstone project for the **MIT Data Science and Machine Learning Program**. While the business case and dataset may have been used in other instructional contexts, this analysis, including all preprocessing, exploratory data analysis (EDA), modeling, and interpretation, was independently developed.

## Business Context

Understanding customer personality and behavior is pivotal for businesses aiming to enhance customer satisfaction and drive revenue growth. Segmentation—based on a customer's demographics, lifestyle, and purchasing behavior—allows companies to move beyond generic strategies. It enables the creation of tailored marketing campaigns, improves customer retention by identifying and nurturing high-value groups, and helps optimize product offerings and resource allocation.

A leading retail company with a rapidly growing customer base seeks to gain deeper insights into their customers' profiles. The company recognizes that understanding customer personalities, lifestyles, and purchasing habits can unlock significant opportunities for personalizing marketing strategies and creating loyalty programs. These insights can help address critical business challenges, such as improving the effectiveness of marketing campaigns, identifying high-value customer groups, and fostering long-term relationships with customers.

With competition intensifying in the retail space, a shift from generalized approaches to more targeted and personalized engagement is essential for sustaining a competitive edge.

---

## Project Objective

In an effort to optimize marketing efficiency and enhance the overall customer experience, this project embarks on a mission to identify distinct customer segments within the provided dataset. By understanding the unique characteristics, preferences, and behaviors of each identified group, the primary aims are to provide a data-driven foundation for the company to:

1.  Develop personalized marketing campaigns designed to increase conversion rates.
2.  Formulate effective retention strategies specifically for high-value customers.
3.  Optimize resource allocation, potentially informing decisions related to inventory management, pricing strategies, and even store layouts.

As the data scientist for this project, my responsibility is to meticulously analyze the customer data, apply K-Means clustering to segment the customer base, and ultimately provide actionable insights and clearly defined personas for each segment.

---
## Dataset

The project utilizes the `marketing_campaign.csv` dataset, which includes information on:
* **Customer Demographics:** Age (derived from Year_Birth), Education, Marital Status, Income, presence of kids/teens in the household.
* **Spending Habits:** Amount spent on various product categories (wines, fruits, meat, fish, sweets, gold products) in the last two years.
* **Purchase Behavior:** Number of purchases made through different channels (web, catalog, store), number of purchases made with a discount, and recency of the last purchase.
* **Campaign Engagement:** Responses to previous marketing campaigns and the outcome of the last campaign.

The dataset initially contained 2240 customer records and 29 features. After cleaning and preprocessing for clustering, 2213 customer records were analyzed.

---
## Methodology

The project followed a structured data science workflow:

1.  **Data Cleaning & Preprocessing:**
    * Loaded the dataset and performed an initial inspection.
    * Handled missing values (primarily in the `Income` column by dropping rows).
    * Engineered an `Age` feature from `Year_Birth`.
    * Identified and handled extreme outliers in `Age`.
    * Dropped irrelevant/redundant columns.
    * Consolidated rare `Marital_Status` categories into an "Other" category.
2.  **Exploratory Data Analysis (EDA):**
    * Conducted univariate and bivariate analysis to understand feature distributions and relationships.
3.  **Data Preparation for K-Means Clustering:**
    * **One-Hot Encoding:** For categorical features (`Education`, `Marital_Status`).
    * **Log Transformation:** Applied to skewed numerical features (e.g., `Income`, spending columns).
    * **Feature Scaling:** Standardized all features using `StandardScaler`.
4.  **Determining Optimal Number of Clusters (k):**
    * Utilized the Elbow Method, Silhouette Score, Davies-Bouldin Index, and Calinski-Harabasz Index.
    * **k=3** was selected as the optimal number of clusters.
5.  **K-Means Clustering & Persona Development:**
    * Applied K-Means algorithm with `n_clusters=3`.
    * **Cluster Profiling:** Analyzed each cluster based on numerical feature means and categorical feature distributions.
    * **Visualization:** Used Plotly for interactive box plots and bar charts.
    * Developed detailed personas for each segment.
6.  **Strategic Recommendations & Business Opportunities:** Identified tailored strategies for each segment and broader business implications.

---
## Key Findings: Identified Customer Segments

Three distinct customer segments were identified:

1.  **Segment 0: "The Affluent Achievers"** (N=1110, approx. 50%)
    * **Profile:** Highest income, oldest, highly educated, few young children.
    * **Behavior:** Highest spenders across all categories & channels, most campaign responsive, low deal usage.
2.  **Segment 1: "The Family-Focused Navigators"** (N=1049, approx. 47%)
    * **Profile:** Middle-low income, middle-aged, households with children/teens, highly educated.
    * **Behavior:** Cautious spenders, high web visit frequency, moderate deal usage & recent campaign response.
3.  **Segment 2: "The Young & Thrifty Explorers"** (N=54, approx. 2.4%)
    * **Profile:** Youngest, lowest income, **Basic education**, households with young children, higher proportion single.
    * **Behavior:** Very low spenders, highest deal usage, highest web visit frequency, least campaign responsive. (Niche segment).

---
## Tools and Libraries Used

* **Python 3.x**
* **Pandas:** Data manipulation and analysis.
* **NumPy:** Numerical operations.
* **Scikit-learn:** K-Means clustering, PCA, StandardScaler, evaluation metrics.
* **Plotly (Express & Graph Objects):** Interactive visualizations.
* **Scikit-learn Metrics:** Manual validation of optimal k using Inertia, Silhouette Score, Davies-Bouldin Index, and Calinski-Harabasz Score.

---
## File Structure

* `01_customer_segmentation_kmeans.ipynb`: The main Jupyter Notebook containing all code, analysis, visualizations, and interpretations.
* `02_customer_segmentation_report.html`: An HTML export of the Jupyter Notebook for easy viewing.
* `03_marketing_campaign_data.csv`: The raw dataset used for this project.
* `README.md`: This file, providing an overview of the project.

---
## How to Use/Reproduce

1.  Ensure you have Python and the listed libraries installed in your environment.
2.  Place the `03_marketing_campaign_data.csv` file in the same directory as the notebook or update the file path in the notebook.
3.  Open and run the `01_customer_segmentation_kmeans.ipynb` notebook in a Jupyter environment (e.g., Jupyter Lab, Jupyter Notebook, Google Colab, VS Code).

---
*Author: Arif Pazhwak*
