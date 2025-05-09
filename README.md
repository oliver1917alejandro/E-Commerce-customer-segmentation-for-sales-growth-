# 📊 E-commerce Data Analysis and Customer Segmentation (RFM) 🛍️

This project performs a comprehensive analysis of an e-commerce dataset to understand customer behavior and segment them using the RFM (Recency, Frequency, Monetary Value) model. The main objective is to identify different customer groups to apply personalized and effective marketing strategies.

## 🎯 Project Description

The Python script (`your_script_name.py`) is designed to perform the following key tasks:

1.  💧 **Data Loading:** Import multiple CSV files containing detailed information about:
    * Customers
    * Orders
    * Products
    * Payments
    * Geolocations
    * Sellers
    * Order Items
    * Order Reviews
2.  🧹 **Data Cleaning and Preparation (Data Wrangling):**
    * Verification and reporting of missing values in each dataset.
    * Identification and removal of duplicate records.
    * Conversion of date/time columns to `datetime` format for temporal analysis.
    * Basic exploratory analysis of prices (average, minimum, maximum).
    * Translation of product category names from Portuguese to English for consistency.
    * Feature engineering: Creation of new useful columns such as month and year of purchase, and calculation of delivery time.
3.  📈 **RFM Analysis (Recency, Frequency, Monetary Value):**
    * Calculation of:
        * **Recency (R):** Days elapsed since the customer's last purchase.
        * **Frequency (F):** Total number of purchases made by the customer.
        * **Monetary Value (M):** Total spending by the customer.
    * Segmentation of customers into 5 significant categories based on their RFM scores:
        * 🌟 **Champions**
        * 💖 **Loyal Customers**
        * 💡 **Potential Loyalist**
        * ⚠️ **At Risk**
        * 😥 **Need Attention**
4.  🖼️ **Results Visualization:**
    * Generation of charts to illustrate the distribution of customers by each RFM segment.
        * *Visualization of segment distribution:*
            ![RFM Segment Distribution](segmentos_rfm.png)
    * Visualization of the average Recency, Frequency, and Monetary Value metrics for each segment, allowing a clear comparison of their characteristics.
        * *Average RFM metrics per segment:*
            ![Average Metrics per RFM Segment](metricas_por_segmento.png)
5.  📤 **Exporting Results:**
    * Saving the RFM segmentation table, with each customer assigned to a segment, to a CSV file (`customer_rfm_segmentation.csv`). This file is ideal for use in targeted marketing campaigns or other subsequent analyses.
    * Saving the generated visualizations as image files (`segmentos_rfm.png`, `metricas_por_segmento.png`).

## 📚 Datasets Used

The analysis is based on the following data files, from the [Olist E-Commerce dataset on Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce):

* `olist_customers_dataset.csv`
* `olist_geolocation_dataset.csv`
* `olist_order_payments_dataset.csv`
* `olist_products_dataset.csv`
* `olist_sellers_dataset.csv`
* `olist_orders_dataset.csv`
* `olist_order_items_dataset.csv`
* `olist_order_reviews_dataset.csv`
* `product_category_name_translation.csv`

## ⚙️ Requirements

To run this project, you will need **Python 3.x** installed along with the following essential libraries:

* **pandas:** For data manipulation and analysis.
* **numpy:** For numerical operations.
* **matplotlib:** For creating static charts.
* **seaborn:** For creating more attractive statistical visualizations.

🔑 Key Analysis Results

📊 Missing Values Identified (Before Specific Treatment):
We have identified the presence of missing values in several of the main datasets, which is a crucial step before proceeding with deeper analyses:

`olist_products_dataset.csv`: 2,448 records were found with missing values in columns considered critical for the analysis.

`olist_orders_dataset.csv`: Presents 4,908 records with missing values.

`olist_order_reviews_dataset.csv`: Contains a significant number of missing values, reaching 145,903 records.
(Note: The current script allows for the identification of these missing values. Specific imputation or deletion strategies can be implemented according to the requirements of the subsequent analysis).

Price Analysis (On `olist_order_items_dataset.csv`):
A quick look at the distribution of item prices reveals the following:

Average item price: $120.65 BRL

Minimum item price: $0.85 BRL

Maximum item price: $6735.00 BRL

📏 Data Dimensions (Post-Initial Cleaning and Main Merge for RFM):
After the initial cleaning process and the necessary dataset merging for RFM analysis, we have the following dimensions:

Unique customers analyzed for RFM: 98,666

📈 RFM Analysis Results:
Applying the RFM (Recency, Frequency, Monetary Value) model to our customer base yields the following average metrics:

Average Recency: Approximately 289 days. This suggests that, on average, customers made their last purchase about 9 months ago within the analyzed data period.

Average Frequency: Is 1.0. This value indicates that the vast majority of analyzed customers have made a single purchase. This is a common pattern in some e-commerce business models or during specific time periods.

Average Monetary Value: Stands at approximately $137.75 BRL per customer.

Customer Distribution by Segment:

🌟 Champions: 35,592 customers
💡 Potential Loyalist: 19,965 customers
💖 Loyal Customers: 19,540 customers
⚠️ At Risk: 19,393 customers
😥 Need Attention: 4,176 customers

Segment Characteristics (Averages):

| Segment             | Average Recency (days) | Average Frequency | Average Monetary Value (BRL) | Brief Description                                   |
|---------------------|------------------------|-------------------|------------------------------|-----------------------------------------------------|
| 🌟 Champions        | 136                    | 1.0               | $153                         | Most recent customers, spending above average.      |
| 💖 Loyal Customers  | 255                    | 1.0               | $131                         | Purchased a moderate time ago, average spending.    |
| 💡 Potential Loyalist | 348                    | 1.0               | $139                         | Purchased longer ago, average spending.             |
| ⚠️ At Risk          | 493                    | 1.0               | $140                         | Haven't purchased in a long time, average spending. |
| 😥 Need Attention   | 528                    | 1.0               | $25                          | Oldest customers with the lowest spending.          |

📢 Suggested Marketing Recommendations
Based on RFM segmentation, the following strategies can be proposed:

🌟 Champions:
Implement VIP loyalty programs.
Offer early access to new products or collections.
Encourage them to become brand ambassadors (e.g., through reviews or referrals).

💖 Loyal Customers:
Encourage cross-selling and up-selling with complementary or higher-value products.
Implement referral programs to attract new customers.
Request product and service reviews.

💡 Potential Loyalist:
Send personalized offers based on their previous purchase history.
Offer incentives to increase purchase frequency (e.g., discounts for a second purchase).
Communicate news and benefits of continued shopping.

⚠️ At Risk:
Launch reactivation campaigns with special discounts or exclusive promotions.
Remind them of the brand's value and benefits.
Conduct surveys to understand why they haven't returned to purchase.

😥 Need Attention:
Send friendly reminders and very attractive "welcome back" offers.
Offer a significant incentive to encourage a repurchase and assess if they can be recovered.
Consider whether it is cost-effective to try to reactivate all customers in this segment or focus on those with greater past spending potential.

🚀 Future Improvements / Next Steps
Advanced Missing Value Handling: Implement more robust strategies such as multiple imputation or predictive models to fill in missing data.
Outlier Analysis: Perform a more detailed outlier analysis on RFM metrics and apply treatment techniques if necessary (e.g., winsorization).
RFM Segmentation Optimization: Explore different scoring methods (e.g., based on fixed percentiles or k-means clustering on RFM metrics) and vary the number of thresholds/segments.
Deepen EDA:
Analysis of best-selling products by segment.
Geographic analysis of customers and its impact on purchasing behavior.
Identification of temporal trends in sales and customer behavior.
Analysis of the effectiveness of different payment methods.
Predictive Modeling:
Develop models to predict customer churn (Churn Prediction).
Estimate Customer Lifetime Value (CLV).
Build product recommendation systems.

