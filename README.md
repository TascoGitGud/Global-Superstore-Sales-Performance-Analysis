# 📊 Power BI | Global Superstore Sales Performance Dashboard 

![Power BI](https://img.shields.io/badge/Tool-Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/Status-Completed-success?style=flat-square)

<p align="center">
  <img src="Images/banner.png" width="100%">
</p>

_Help a Senior Manager understand the overall business performance, compare markets, and identify which products to grow or cut - all in one interactive dashboard._

- 🎯 **Business Question:** What is the overall business performance, how are different markets doing, and which products should the company focus on?
- 🏬 **Domain:** Global Retail / E-commerce 
- 🛠️ **Tools:** Power BI

👤 Author: Bạch Minh Nam

---

## 📑 Table of Contents
1. [📌 Background & Overview](#-background--overview)
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)
3. [🧠 Design Thinking Process](#-design-thinking-process)
4. [📝 Key Findings & Visualizations](#-key-findings--visualizations)
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---

## 📌 Background & Overview

### 🎯 Business Problem

Global Superstore is a company that sells products in many markets across different continents. The company is growing fast and wants to expand into more markets to gain market share.

The Senior Manager needs a dashboard to answer 3 main questions:

✔️ **Overall Performance:** How is the business doing right now? Is revenue and profit growing?

✔️ **Market Performance:** Which markets are performing well, and which ones need attention?

✔️ **Product Performance:** Which product categories are profitable, and which ones should be prioritized or cut?

This project uses Power BI to turn raw sales data into a dashboard that helps the Senior Manager make faster, data-driven decisions about where to expand and which products to invest in.

### 👤 Who is this project for?

✔️ Senior Managers & Business Directors - to get a quick, reliable view of company performance

✔️ Sales & Market teams - to compare performance across regions and plan strategy

✔️ Product teams - to identify which categories or products drive (or hurt) profit

---

## 📂 Dataset Description & Data Structure

### 📌 Data Source
- Source: Global Superstore Sales dataset (loaded via Google BigQuery)
- Format: Live connection / Power Query

### 📊 Data Structure & Relationships

#### 1️⃣ Data Structure

The dataset has **3 tables**:

<details>
<summary><b>📋Table 1: Orders</b> - Main fact table storing all sales transaction details</summary>
  
| Column Name | Description |
|---|---|
| `Order ID` | Unique ID for each order |
| `Order Date` | Date the order was placed |
| `Ship Date` | Date the order was shipped |
| `Ship Mode` | Shipping method |
| `Customer ID` | Unique ID for each customer |
| `Customer Name` | Name of the customer |
| `Segment` | Customer segment |
| `City` | City of the customer |
| `State` | State/Province of the customer |
| `Country` | Country of the customer |
| `Postal Code` | Postal code of the customer's location |
| `Market` | Market region |
| `Region` | Sub-region within a market |
| `Product ID` | Unique ID for each product |
| `Category` | High-level product category |
| `Sub-Category` | More specific product grouping under a category |
| `Product Name` | Name of the product |
| `Sales` | Total sales value of the order line |
| `Quantity` | Number of units ordered |
| `Discount` | Discount rate applied to the order |
| `Profit` | Profit earned from the order |
| `Shipping Cost` | Cost to ship the order |
| `Order Priority` | Priority level of the order |
 
</details>
<details>
<summary><b>👤 Table 2: People</b> - Stores salesperson and regional assignments</summary>
  
| Column Name | Description |
|---|---|
| `Person` | Name of the salesperson |
| `Region` | Region this person is responsible for |
 
</details>
<details>
<summary><b>↩️ Table 3: Returns</b> - Records product returns by order</summary>
  
| Column Name | Description |
|---|---|
| `Order ID` | Order that was returned |
| `Returned` | Yes/No flag indicating if order was returned |
 
</details>

#### 2️⃣ Data Relationships

The 3 tables are connected as follows:

- `People` → `Orders`: One person manages many orders (1-to-many, joined on `Region`)
- `Orders` → `Returns`: One order can have one return record (joined on `Order ID`)

<p align="center">
  <img src="Images/data_model.png" width="80%">
</p>

---

## 🧠 Design Thinking Process

This project followed the Design Thinking framework across 2 main steps: Empathize and Define Point of View

### 1️⃣ Empathize - Understanding the Stakeholder

<p align="center">
  <img src="Images/Step_1.png" width="100%">
</p>

### 2️⃣ Define Point of View - Choosing the Right Angles

<p align="center">
  <img src="Images/Step_2.png" width="100%">
</p>

### **⭐ Northstar Metrics:**

<p align="center">
  <img src="Images/Northstar.png" width="100%">
</p>

> 📄 For the full Design Thinking breakdown, see [Global Superstore Sales Design Thinking ](Design_Thinking_Global_Superstore_Sales.pdf)

---

## 📝 Key Findings & Visualizations  

-- chỉ là format , nội dung chưa hoàn chỉnh

### 🔍 Dashboard Preview

#### 1️⃣ Page 1 - Performance Overview

<p align="center">
  <img src="Images/Page_1.png" width="100%">
</p>

**📈 Key Findings:**

- Revenue and profit both increased by over 50% compared to the previous year, showing strong overall growth
- Profit margin has remained stable at around 11.6%, indicating consistent operational efficiency
- Return rate has been rising year-over-year since 2012, which could gradually impact profitability despite growing order volumes
- Furniture generates decent revenue but has a significantly lower profit margin compared to the Technology category

#### 2️⃣ Page 2 - Market Analysis

<p align="center">
  <img src="Images/Page_2.png" width="100%">
</p>

**🌍 Key Findings:**

- APAC and EU are the largest revenue drivers, which aligns with their size as major markets
- Canada, despite being the smallest market, achieves the highest profit margin at 26.62%
- EMEA has the lowest profit margin among major markets and experiences the highest return rate at 6.2%
- EMEA's average order value fluctuates significantly year-to-year, suggesting unstable market performance

#### 3️⃣ Page 3 - Product Analysis

<p align="center">
  <img src="Images/Page_3.png" width="100%">
</p>

**📦 Key Findings:**

- Tables generates substantial revenue (approximately 0.76M) but operates at a loss with negative profit
- Paper and Labels have the highest profit margins (24.24% and 20.45% respectively) but contribute less to total revenue
- APAC and EU account for the majority of sales across nearly all product categories
- High-margin products like Paper and Labels are underutilized compared to their profit potential

---

## 🔎 Final Conclusion & Recommendations

**💡 Recommendations:**

✔️ **Best expansion candidates: Canada & LATAM.** Canada demonstrates the highest profit margin at 26.62% while remaining the smallest market, indicating significant growth potential without sacrificing efficiency. LATAM presents the second-best opportunity with solid revenue growth and more consistent average order values compared to EMEA or Africa. These markets offer the optimal balance of low risk and strong returns for expansion.

✔️ **Pair expansion strategy with high-margin products.** When expanding into Canada and LATAM, prioritize sub-categories with strong margins such as Paper and Labels rather than focusing on high-volume products from established markets. This approach combines efficient market positioning with efficient products to establish strong profitability from the start.

✔️ **Resolve EMEA operational challenges before further expansion.** EMEA currently shows the lowest profit margins and highest return rates among major markets, with volatile average order values. Scaling investment in this market without addressing these issues would amplify existing problems rather than drive growth.

✔️ **Address increasing return rates to protect future growth.** The return rate has risen consistently since 2012, which threatens profit growth even as revenue increases. This issue becomes more critical as the company expands into new markets.

✔️ **Stabilize the product portfolio before scaling operations.** Tables currently operates unprofitably and should be excluded from expansion plans until its cost and pricing challenges are resolved. Meanwhile, high-margin products like Paper and Labels should be positioned as growth drivers in new market entries.

---
