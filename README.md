# Retail Sales Analytics

## 📌 Project Overview

This project analyzes retail sales data to understand sales performance, profitability, and the factors contributing to differences in profit margins across stores, cities, and products.

The analysis started with overall sales and profit performance and gradually moved into a deeper investigation of a low-margin store-category combination.

The main investigation focused on **Bengaluru Grocery**, where profit margins were comparatively lower than other store combinations.

---

## 🎯 Business Problem

The initial question was:

> **Why is the Grocery category generating relatively poor profit margins?**

To investigate this, I analyzed several possible factors, including:

* Discounts
* Product mix
* Quantity
* Returns
* Payment modes
* Store-level performance
* Product-level margins
* Selling price
* Cost structure

The goal was not just to identify that margins were low, but to investigate **what was driving the difference**.

---

## 📊 Dataset

The dataset contains approximately **8,000 retail transactions** with information about:

* Date
* Store ID
* Store City
* Product ID
* Category
* Customer ID
* Sales
* Quantity
* Profit
* Discount
* Payment Mode
* Returned

The dataset contains **no missing values**.

---

## 🔎 Analysis Workflow

### 1. Exploratory Data Analysis

I first examined:

* Sales performance across cities
* Category-level sales
* Profit performance
* Profit margins
* Store and product performance

Visualizations were created using **Matplotlib and Seaborn**.

### 2. Profit Margin Analysis

Profit margin was calculated as:

`Profit Margin = Profit / Sales`

This helped compare profitability rather than looking only at total sales or profit.

The analysis revealed that **Bengaluru Grocery had a comparatively lower margin**, which became the focus of the deeper investigation.

### 3. Discount Investigation

I investigated whether excessive discounting was responsible for the lower margin.

The analysis did **not show a clear monotonic relationship between discount and profit margin**, so excessive discounting was not supported as the primary explanation.

### 4. Returns Investigation

Bengaluru had the lowest return rate among the cities analyzed.

A **Mann–Whitney U test** was also performed to compare profit margins between returned and non-returned transactions in Bengaluru.

The result was not statistically significant, suggesting that returns were not a meaningful explanation for the margin difference.

### 5. Payment Mode Investigation

Profit margins were compared across:

* Card
* Cash
* UPI

A **Kruskal–Wallis test** produced a non-significant result, indicating that payment mode did not explain the observed margin difference.

### 6. Store-Level Investigation

The analysis was then narrowed down to individual stores within Bengaluru Grocery.

This revealed that **S001 had a particularly low profit margin compared with the other Bengaluru stores**.

The investigation was therefore taken further into product-level performance.

### 7. Product-Level Investigation

Products were compared across stores to identify products where S001 consistently showed weaker margins.

This resulted in a set of **11 products with meaningful margin differences** between S001 and the other stores.

### 8. Price and Cost Investigation

For these products, I compared:

* Profit margin difference
* Unit price difference
* Cost difference

The analysis showed that price and cost differences moved very strongly together, while their individual relationship with margin difference was considerably weaker.

The correlation between **Price Difference and Cost Difference was approximately 0.999**.

This suggests that the margin problem is more closely related to the **underlying price/cost structure** than to the previously investigated factors such as discounting, returns, or payment mode.

---

## 💡 Key Findings

* Bengaluru Grocery showed comparatively lower profit margins.
* Excessive discounting was **not supported** as the main cause.
* Returns did not show a statistically significant relationship with profit margin.
* Payment mode did not significantly explain margin differences.
* Store-level analysis identified **S001** as a particularly weak-performing store.
* Product-level analysis identified **11 products** with meaningful margin gaps.
* Price and cost differences were extremely strongly correlated.
* The investigation ultimately shifted from operational factors toward **product-level price and cost structure**.

---

## 🛠️ Tools & Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy
* Jupyter Notebook
* GitHub

---

## 📁 Project Structure

```text
Retail-Sales-Analytics/
│
├── Retail_Sales_Analytics_Dataset.xlsx
├── retail_sales_analysis.ipynb
└── README.md
```

---

## 📈 What I Learned

This project helped me practice a complete analytical workflow:

**Business Question → EDA → Hypothesis → Investigation → Statistical Testing → Deeper Analysis → Business Insight**

A key learning from this project was that identifying a correlation or pattern is only the beginning. The important part is progressively investigating possible explanations and using evidence to eliminate unsupported hypotheses.

---

## 🚀 Future Improvements

Possible extensions of this project include:

* Building an interactive dashboard
* Performing more detailed product-level price optimization
* Building a predictive model for profit margin
* Developing automated store performance monitoring
* Investigating pricing strategies across cities and stores
