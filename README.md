# E-Commerce Fulfillment Optimization & Logistics Pipeline

An end-to-end data engineering and analytics pipeline built to audit, sanitize, and extract critical business insights from messy, multi-format supply chain transaction logs.

## 🚀 Live Environment
* **Interactive Notebook:** [Open Project in Google Colab](https://colab.research.google.com/drive/1tlTLAdKHJ2PVO0Jlq8qttopA84VYYmrg?usp=sharing)

---

## 🎯 Executive Business Insights

### 1. Revenue Backlog & Financial Exposure
* **Insight:** Identified **$9,400.00** in total customer transaction value currently trapped in a `Delayed` delivery status. 
* **Business Action:** This represents unrealized revenue and high customer churn risk. A targeted dispatch audit is required for pending backlogs.

### 2. Operational Bottlenecks (Carrier Shipping Lag)
Our data pipeline calculated the exact delivery turnaround time across various fulfillment companies once shipments leave the warehouse gates:
* **VelocityAir:** 1.5 Days (Highly Efficient)
* **SwiftCargo:** 3.0 Days (Standard Baseline)
* **LogiPost:** **6.2 Days (Severe Operational Bottleneck)**

<p align="center">
  <img src="carrier_performance.png" width="600" alt="Carrier Performance Chart">
</p>

* **Business Action:** **LogiPost takes more than double the time** of our standard carrier. Management should renegotiate service level agreements (SLAs) or aggressively shift shipping volume toward VelocityAir to reduce delivery lag by up to 75%.

### 3. Inventory Mix & Volume Drivers
* **Insight:** Order volume is heavily concentrated. **Security products (38.1%)** and **Smart Lighting (31.8%)** combine to drive nearly **70% of total company transactions**.

<p align="center">
  <img src="product_distribution.png" width="650" alt="Product Distribution Chart">
</p>

* **Business Action:** Because these two categories dictate our cash flow, any delivery delays associated with Security or Lighting components will disproportionately harm brand loyalty. Supply chains for these specific parts must be heavily guarded against disruptions.

---

## 🛠️ Data Engineering Achievements
* **Deceptive Multi-Format Date Trap Resolved:** Fixed an underlying systemic flaw where text string dates were written interchangeably as `DD/MM/YYYY` and `YYYY-MM-DD`, causing fatal mathematical row misalignments and negative numbers.
* **Upfront Data Sanitization:** Implemented a unified row-by-row mapping function using Python and Pandas to enforce strict temporal schemas and eliminate structural string anomalies during the initial ingest phase.
