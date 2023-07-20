<div align="center">
<h1>
  FLO Customer Segmentation
</h1>

<h4>
    <img alt="FLO" src="https://github.com/bekowashere/rfm-flo/blob/main/src/flo1.png?raw=true">
</h4>
</div>



## Used technologies

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white) ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)

## Business Problem

FLO, an online shoe store, wants to segment its customers and determine marketing strategies according to these segments. For this purpose, the behaviors of the customers will be defined and groups will be formed according to the clusters in these behaviors.

## Data Set Story

The dataset consists of information obtained from the past shopping behaviors of customers who made their last purchases from FLO as OmniChannel (both online and offline shopper) in the years 2020-2021.

| Variable  | Definition   |
|---|---|
|   **master_id**  | Unique customer number |
|   **order_channel**  | Which channel of the shopping platform is used (Android, IOS, Desktop, Mobile) |
|   **last_order_channel**  | The channel where the most recent purchase was made |
|   **first_order_date**  | Date of the customer's first purchase |
|   **last_order_date**  | Customer's last purchase date |
|   **last_order_date_online**  | The date of the last purchase made by the customer on the online platform |
|   **last_order_date_offline**  | Last shopping date made by the customer on the offline platform |
|   **order_num_total_ever_online**  | The total number of purchases made by the customer on the online platform |
|   **order_num_total_ever_offline**  | Total number of purchases made by the customer offline |
|   **customer_value_total_ever_offline**  | Total fee paid by the customer for offline purchases  |
|   **customer_value_total_ever_online**  | The total fee paid by the customer for their online shopping |
|   **interested_in_categories_12**  | List of categories the customer has shopped in the last 12 months |

## Project Tasks

### TASK 1: Data Understanding and Preparation

- **Step 1:** Read the flo_data_20K.csv data. Make a copy of the dataframe.
- **Step 2:** Make the following analyzes on the data set:
    - **a.** The first 10 observations
    - **b.** Variable names
    - **c.** Descriptive statistics
    - **d.** Null value
    - **e.** Variable types
- **Step 3:** Omnichannel means that customers shop from both online and offline platforms. Create new variables for each customer's total purchases and spending.
- **Step 4:** Examine the variable types. Change the type of variables that express date to date.
- **Step 5:** Look at the distribution of the number of customers in the shopping channels, the total number of products purchased, and the total expenditures.
- **Step 6:** List the top 10 customers with the highest revenue.
- **Step 7:** List the top 10 customers with the most orders.
- **Step 8:** Functionalize the data preprocessing process.

### TASK 2: Calculating RFM Metrics

- **Step 1:** Make the definitions of **Recency**, **Frequency** and **Monetary**.
- **Step 2:** Calculate the Recency, Frequency and Monetary metrics specific to the customer.
- **Step 3:** Assign your calculated metrics to a variable named rfm.
- **Step 4:** Change the names of the metrics you created to recency, frequency and monetary.

**Attention!** You can select the analysis date 2 days after the maximum date to calculate the recency value.

### TASK 3: Calculating RF Scores

- **Step 1:** Convert Recency, Frequency and Monetary metrics to scores between 1-5 with the help of **qcut**.
- **Step 2:** Record these scores as **recency_score**, **frequency_score** and **monetary_score**.
- **Step 3:** Express recency_score and frequency_score as a single variable and save as **RF_SCORE**.

### TASK 4: Segment Definition of RF Scores

- **Step 1:** Make segment definitions for the generated RF scores.
- **Step 2:** Convert the scores into segments with the help of the **seg_map** below.

```python
seg_map = {
    r'[1-2][1-2]': 'hibernating',
    r'[1-2][3-4]': 'at_Risk',
    r'[1-2]5': 'cant_loose',
    r'3[1-2]': 'about_to_sleep',
    r'33': 'need_attention',
    r'[3-4][4-5]': 'loyal_customers',
    r'41': 'promising',
    r'51': 'new_customers',
    r'[4-5][2-3]': 'potential_loyalists',
    r'5[4-5]': 'champions',
}
```

### TASK 5: Time for Action

- **Step 1:** Examine the recency, frequency and monetary averages of the segments.
- **Step 2:** With RFM analysis, find the customers in the relevant profile for 2 cases and save the customer IDs to csv.
    - **a.** FLO includes a new women's shoe brand. The product prices of the brand it includes are above the general customer preferences. For this reason, customers in the profile who will be interested in the promotion of the brand and product sales are requested to be contacted privately. From their loyal customers(champions,loyal_customers), the customers who shop in the women category will be contacted privately. Save the id numbers of the customers to the csv file as **new_brand_target_customer_id.cvs**.
    - **b.** Up to 40% discount is planned for Men's and Children's products. We want to specifically target customers who are good customers in the past who are interested in categories related to this discount, but have not shopped for a long time and new customers. Save the ids of the customers in the appropriate profile to the csv file as **discount_target_customer_ids.csv**.