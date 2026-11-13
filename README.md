# 🛒 E-Commerce Sales & Behavioral Performance Analytics

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1aWmcGoLm0rxBfdwKAlGPOpJMJsPZEc0A?usp=drive_link)
[![Tableau Public](https://img.shields.io/badge/Tableau-Public-blue?logo=tableau)](https://public.tableau.com/views/E-commerceEnd-to-EndPerformanceDashboard/Dashboard-Overview1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

An end-to-end Python data analytics project exploring multi-channel e-commerce sales performance, customer behavioral segmentation, traffic acquisition efficiency, and statistical hypothesis testing.

---

## 📌 Project Overview & Objectives

The goal of this project is to clean, transform, aggregate, and statistically evaluate transactional data to uncover key revenue drivers, user engagement patterns, and channel effectiveness.

### Core Business Questions Addressed:
1. **Traffic & Revenue Dynamics:** What is the statistical relationship between daily website traffic volume and total sales revenue?
2. **User Segmentation & Guest Checkout:** How do registered vs. unregistered (guest) users contribute to total sales volume and conversion behavior?
3. **Geographic & Category Concentration:** Which regional markets and product categories generate the highest margins and demand?
4. **Acquisition Channels & Device Ecosystem:** Which marketing channels and device types drive primary traffic and revenue scale?
5. **Statistical Rigor:** Do key metrics follow normal distributions, and what non-parametric tests validate our behavioral findings?

---

## 🛠️ Data Pipeline & Project Workflow

The project follows a rigorous Data Analytics Lifecycle:

### 1. Data Ingestion & Schema Exploration
* **Source Datasets (BigQuery):** Merged relational tables across sessions, session parameters, accounts, orders, and product catalogs (`data-analytics-mate.DA`).
* **Dataset Scale:** 349,545 total session records spanning multi-month e-commerce operations.

### 2. Data Cleaning & Preprocessing
* **Missing Value Analysis:** Evaluated null proportions across user and product attributes; isolated monetary evaluations to dedicated transaction datasets (`orders_df`).
* **Guest User Handling:** Assigned sentinel value `-1` to missing user IDs to explicitly analyze unregistered guest sessions (accounting for ~92.01% of records).
* **Type Conversion & Normalization:** Standardized order dates to datetime formats and categorized missing categorical descriptors as 'unknown'.

### 3. Statistical Testing & Non-Parametric Framework
* **Normality Testing:** Confirmed right-skewness and rejected normality across key metrics using **Shapiro-Wilk** and **Normaltest** ($p < 0.05$).
* **Advanced Evaluation:** Applied non-parametric methods including **Spearman rank correlation** ($r_s$) and **Kruskal-Wallis** tests to evaluate non-normal distributions safely.

### 4. Exploratory Data Analysis (EDA) & Feature Engineering
* **Core Metrics:** Calculated total sales, order frequency, average order value (AOV), and channel shares.
* **Temporal & Weekly Seasonality:** Extracted day-of-week patterns uncovering mid-week demand peaks and weekend drop-offs.
* **Cross-Regional Co-Movement:** Evaluated regional demand synchronization across continental markets.

---

## 💻 Tech Stack & Python Libraries

* **Environment:** Google Colab / Jupyter Notebook
* **Data Wrangling & SQL:** `pandas`, `numpy`, `google-cloud-bigquery`
* **Statistical Analysis:** `scipy.stats` (Shapiro-Wilk, Spearmanr, Normaltest)
* **Data Visualization:** `matplotlib`, `seaborn` (custom dark-theme palettes, grid formatting, desynced spines)
* **BI & Dashboarding:** Tableau Public

---

## 📊 Business Key Takeaways & Findings

* **Traffic as a Primary Proxy:** A near-perfect monotonic correlation exists between daily site sessions and total sales ($r_s = 0.9510$, $p = 1.35 \times 10^{-45}$).
* **Guest Checkout Dominance:** Unregistered guest users represent the overwhelming majority of revenue and order volume, highlighting the need for frictionless non-registered checkout funnels.
* **Geographic & Category Core:** The US market acts as the primary revenue engine (~$13.94M), anchored by a core product triad: **Sofas & armchairs** ($8.39M), **Chairs** ($6.15M), and **Beds** ($4.92M).
* **Channel & Device Performance:** Organic Search and Paid Search lead acquisition channels, while Desktop devices capture ~59% of total sales revenue across Chrome and Safari ecosystems.

---

## 🔗 Interactive Dashboards & Access

* You can view the full Google Colab code implementation and statistical breakdown here: 👉 [Open Google Colab Notebook](https://colab.research.google.com/drive/1aWmcGoLm0rxBfdwKAlGPOpJMJsPZEc0A?usp=drive_link)
* Explore the interactive multi-page visual reports here: 👉 [View Tableau Public Dashboard](https://public.tableau.com/views/E-commerceEnd-to-EndPerformanceDashboard/Dashboard-Overview1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
