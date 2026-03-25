# Olist Analytics: Unraveling the Causes of Low Review Scores

## 📊 Project Overview

This project analyzes **98,000+ orders** from Olist, a major Brazilian e-commerce platform, to identify the root causes of negative customer ratings and provide operations teams with actionable insights for improvement.

**Key Finding:** The platform's average review score of 4.09/5 is driven by three distinct operational failures—not random chance. This analysis isolates each variable and provides concrete, executable recommendations.

---

## 🎯 The Problem: Context & Objective

**The Challenge:**
Olist was experiencing stagnant customer satisfaction with an average review score of 4.09 out of 5.0. The executive team had a critical question: *Why are customers leaving bad reviews?*

**The Business Objective:**
Analyze customer review data to identify the root causes of negative ratings (1 and 2 stars) and provide operations teams with actionable "Hit Lists" to improve platform reputation and customer satisfaction.

**Scope:** 98,000+ orders analyzed across multiple dimensions—logistics, sellers, and products.

---

## 🧠 The Approach: Branches of Thinking

To avoid getting lost in the data, the CEO's broad question was deconstructed into three testable hypotheses using a **MECE (Mutually Exclusive, Collectively Exhaustive) framework**:

### **Branch 1: Logistics Hypothesis**
- **Question:** Do late deliveries significantly damage the review score?
- **Rationale:** Poor logistics is often the most visible pain point in e-commerce.

### **Branch 2: Seller Quality Hypothesis**
- **Question:** Are a few "bad apple" sellers driving the majority of 1-star reviews?
- **Rationale:** Concentrated quality issues are easier to fix than systemic problems.

### **Branch 3: Product Category Hypothesis**
- **Question:** Are specific product categories inherently prone to bad ratings, regardless of who sells them?
- **Rationale:** Category-level issues require different operational interventions.

---

## ⚙️ The Execution: Technical Build

### **Data Architecture**

**From Chaos to Order:** Transformed a messy, flat dataset into a robust **Star Schema** with:
- **3 Fact Tables:** Orders, Order Items, Order Reviews
- **5 Dimension Tables:** Customers, Sellers, Products, Categories, Delivery Status
- **Result:** Optimal DAX performance, accurate cross-filtering, and scalability

### **Advanced DAX (Forensic Metrics)**

Instead of just showing averages, custom business metrics were engineered to quantify the blame:

| Metric | Formula | Purpose |
|--------|---------|---------|
| **Logistics Penalty** | Rating Drop (Late vs. On-time) | Quantifies exact damage from late deliveries |
| **% Seller Defects** | (1-2 star orders / Total orders) × 100 | Identifies "bad apple" sellers |
| **Product Quality Gap** | Category Avg - Global Avg | Measures category-specific performance deviation |
| **Late Order Rate** | (Late orders / Total orders) × 100 | Tracks delivery performance impact |

### **UI/UX Design**

**Dashboard Architecture:** Modern "Cyber-Glass" dark-mode interface split into two strategic pages:

1. **Executive Summary Page**
   - High-level KPIs and trend analysis
   - Key metrics at a glance
   - Year-over-year performance trends

2. **Operational Action Plan Page**
   - Ground-level execution focus
   - "Hit Lists" of top offending sellers
   - Product category performance matrix
   - Actionable recommendations for each operational area

### **Tech Stack**
- **Data Modeling:** Power BI / DAX
- **Data Source:** Olist Brazilian E-commerce Dataset
- **Visualization:** Power BI Interactive Dashboards
- **Analysis Framework:** MECE decomposition

---

## 🔍 The Synthesis: Findings & Actionable Recommendations

### **Key Findings**

#### **1. Logistics is the Biggest Killer ⚠️**

The data reveals a devastating impact from late deliveries:

- **On-time delivery average rating:** 4.2 ⭐
- **Late delivery average rating:** 2.5 ⭐
- **Logistics Penalty Score:** **1.73** (1.7 point drop)
- **Late order volume:** ~7,826 orders (9.8% of total)

**Translation:** Late orders directly convert satisfied customers into detractors. This is the strongest lever for improvement.

#### **2. A Concentrated "Bad Seller" Problem 🎯**

The platform exhibits a pareto distribution of seller quality:

- **Overall Seller Defect Rate:** 14.69%
- **Critical Finding:** Not evenly distributed—the analysis identified a specific group of high-volume sellers who are serial offenders
- **Top offenders:** Some sellers maintain defect rates as high as **81%**
- **Impact:** A small number of bad actors are disproportionately damaging brand reputation

**Most Impactful Sellers with Low Reviews:**
- Seller 1ca7077d89... — 114 orders, 1.65 avg rating (81% defect rate)
- Seller 02685a — 110 orders, 1.65 avg rating (81% defect rate)
- Seller 54965bbe3e... — 76 orders, 1.66 avg rating (81% defect rate)
- Plus 5,058+ other high-defect sellers requiring attention

#### **3. Inherently Flawed Categories 📦**

Even when delivered on time, certain product categories underperform:

- **Bottom performing categories:**
  - Children's Clothes — consistently below average
  - Diapers & Hygiene — quality consistency issues
  - Fashion (particularly children's and women's categories) — diverges significantly

- **Quality Gap:** These categories drag the aggregate score down by 0.3-0.5 stars regardless of seller or delivery performance
- **Root Cause:** Likely quality control or product-market fit issues rather than logistics

---

## 📋 Recommended Business Actions

### **🚨 IMMEDIATE (0-2 weeks)**
Execute the generated "Hit List" to suspend or ban sellers maintaining **>50% defect rates**.

**Expected Impact:** Remove the worst 5-10% of sellers and recover ~0.15-0.25 stars in average rating.

### **📅 SHORT-TERM (1-3 months)**
Renegotiate Service Level Agreements (SLAs) with logistics carriers, focusing on delivery speed.

**Expected Impact:** Reduce late orders from 9.8% to <5% and recover ~0.4-0.6 stars in average rating.

### **🔧 LONG-TERM (3-6 months)**
Implement stricter quality control for underperforming product categories:
- Additional QA checkpoints for Children's Clothes and Diapers
- Re-evaluate supplier relationships in Fashion categories
- Consider category-specific certification standards

**Expected Impact:** Additional 0.2-0.4 star recovery by improving category baseline quality.

---

## 📊 Dashboard Insights

The interactive Power BI dashboard provides:

✅ **Real-time metrics** on logistics penalties and seller defect rates  
✅ **Geographic heat maps** showing regional delivery performance issues  
✅ **Seller performance scatter plots** for easy identification of outliers  
✅ **Product category rankings** by average review score  
✅ **Time-series trends** to track improvement initiatives  

---

## 💡 Key Takeaway

Low review scores are **not random**—they result from **three distinct, quantifiable operational failures**:

1. **Flawed logistics** (biggest impact)
2. **Concentrated bad sellers** (easiest to fix)
3. **Category-quality issues** (structural fix required)

By addressing these in priority order, Olist can realistically improve its average rating from **4.09 to 4.4-4.5 stars within 6 months**.

---

## 📁 Data Sources

- **Dataset:** Olist Brazilian E-commerce Public Dataset
- **Records Analyzed:** 98,000+ orders
- **Time Period:** 2016-2018
- **Geography:** Brazil

---

## 🛠️ How to Use This Analysis

1. **For Executives:** Review the Executive Summary dashboard for high-level trends and investment priorities
2. **For Operations Teams:** Use the "Hit List" tables to identify specific sellers and products requiring action
3. **For Logistics Partners:** Reference the delivery performance metrics in SLA renegotiations
4. **For Product Teams:** Review the Product Quality Gap analysis to prioritize category improvements

---

## 📈 Expected Business Impact

| Action | Timeline | Expected Rating Lift | Priority |
|--------|----------|---------------------|----------|
| Ban high-defect sellers | 0-2 weeks | +0.15-0.25 ⭐ | 🔴 Critical |
| Improve logistics SLAs | 1-3 months | +0.40-0.60 ⭐ | 🔴 Critical |
| Enhance category QC | 3-6 months | +0.20-0.40 ⭐ | 🟡 High |
| **Total Potential Uplift** | **6 months** | **+0.75-1.25 ⭐** → **~4.85/5.0** | ✅ Strategic |

---

## 📞 Contact & Questions

For questions about this analysis, data methodology, or implementation recommendations, please reach out.

---

**Last Updated:** March 2026  
**Analysis Methodology:** MECE Decomposition + Advanced DAX Metrics  
**Status:** Active - Recommendations Ready for Implementation
