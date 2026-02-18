# **Impact of COVID-19 on Maternal & Newborn Health**

### **Data-Driven Analysis of Pregnancy Outcomes During the Pandemic**

**Sector:** Healthcare — Maternal & Child Health  
**Course:** Data Visualization & Analytics  
**Faculty Advisor:** Prof. Archit Raj  
**Date:** February 2026

---

## **1. Project Overview**

This project analyzes survey-based data from the *Pregnancy during the COVID-19 Pandemic (PdP)* study conducted in Canada to examine maternal mental health and neonatal outcomes during COVID-19.

**Objectives:**

* Quantify pandemic-related stress and anxiety levels

* Analyze key birth outcomes (Preterm, Birth Weight, NICU Stay)

* Identify demographic and socioeconomic variations

* Build an interactive Google Sheets dashboard for segmented analysis

This project focuses on descriptive and dashboard-based analytics.

---

## **2. Dataset Description**

**Source:** Pregnancy during the COVID-19 Pandemic (PdP) Study  
 **Country:** Canada

### **Data Size**

* Raw dataset: \~10,773 records

* Cleaned dataset: 5,389 records

* Final dataset: \~20 columns after transformation

### **Key Variable Categories**

| Category | Variables |
| ----- | ----- |
| Demographics | Maternal Age, Household Income, Maternal Education |
| Mental Health | EPDS, PROMIS Anxiety |
| Pandemic Stress | Threaten\_Life, Threaten\_Baby\_Danger, Threaten\_Baby\_Harm |
| Birth Outcomes | Gestational Age, Birth Weight, Delivery Mode, NICU Stay |

---

## **3. Data Cleaning & Preparation**

### **Cleaning Steps Performed**

* Rows containing `"UNKNOWN"` values were filtered out.

* Missing numeric values (where applicable) were replaced using median or mode logic.

* Delivery\_Date column was removed from the dataset.

* Extreme values in birth weight and gestational age were reviewed.

* Income categories were converted into numeric midpoints.

### **Feature Engineering**

| Engineered Feature | Logic |
| ----- | ----- |
| Age\_Category | \<25 \= Young, 25–35 \= Adult, \>35 \= High Risk |
| Depression\_Severity | EPDS grouped into Minimal / Moderate / Severe |
| Preterm\_Status | Gestational Age \< 37 weeks |
| Income\_Group | Low / Middle / High |
| Maternal\_Pandemic\_Stress | Weighted combination of threat scores |

---

## **4. Key KPIs (From Dashboard)**

| KPI | Value |
| ----- | ----- |
| Total Deliveries | 5,389 |
| Average Birth Weight | 3,415 g |
| Preterm Birth Count | 307 |
| Preterm Birth Rate | 19.4% |
| NICU Admission Count | 531 |
| NICU Admission Rate | 9.78% |
| Average Anxiety Score | 18.43 / 35 |
| Average Pandemic Stress | 51.54 / 100 |
| C-Section Rate | 29.36% |

These KPIs provide a high-level overview of maternal mental health levels and neonatal outcomes during the pandemic period.

---

## **5. Exploratory Data Analysis Summary**

### **Mental Health Overview**

* Average PROMIS Anxiety score: 18.43 / 35

* Average Pandemic Stress score: 51.34 / 100

* Perceived threat to unborn baby scored higher than perceived threat to mother’s own life

This indicates elevated psychological stress during pregnancy.

---

### **Birth Outcomes**

* Preterm birth rate: 19.4%

* NICU admission rate: 9.78%

* Average birth weight: 3,415 g

* C-Section rate: 29.36%

These metrics quantify neonatal outcome severity in the dataset.

---

### **Age-Based Segmentation**

Pivot analysis shows:

* Young (\<25) and High Risk (\>35) age groups have relatively higher preterm proportions compared to the Adult (25–35) group.

* NICU admissions vary across maternal age categories.

This suggests variation in outcomes across maternal age groups.

---

### **Income & Education Segmentation**

* Lower income groups show a higher proportion of severe depression cases.

* Higher education levels are associated with lower depression and anxiety scores.

This highlights socioeconomic variation in maternal mental health.

---

### **Delivery Mode & NICU**

* C-Section deliveries show higher NICU admission rates compared to vaginal deliveries.

* This reflects variation in neonatal outcomes by delivery type.

---

## **6. Dashboard Structure 📊**

The dashboard was built entirely in Google Sheets using:

* Pivot Tables

* Calculated KPIs

* Interactive slicers

* Dynamic charts

### **Dashboard Components**

**KPI Scorecards**

* Total Deliveries

* Preterm Rate

* NICU Rate

* Avg Anxiety

* Avg Pandemic Stress

**Charts**

* Preterm Distribution by Age Category

* NICU by Delivery Mode

* Depression Severity by Income

* Mental Health by Education

* Pandemic Stress Distribution

**Filters**

* Age Category

* Income Group

* Delivery Mode

* Education Level

The slicers dynamically update KPIs and charts.

---

## **7. Key Insights 💡**

* Anxiety and pandemic stress levels were elevated across the study population.

* Preterm birth rate (19.4%) is higher than national baseline averages.

* Maternal age shows a U-shaped pattern in preterm distribution.

* Lower income groups show higher severe depression prevalence.

* C-Section deliveries have higher NICU admission rates.

* Mothers reported greater concern for their unborn baby than for their own health.

---

## **8. Recommendations**

* Implement routine EPDS and Anxiety screening during prenatal visits.

* Provide targeted mental health support for lower-income groups.

* Introduce age-based prenatal risk flagging.

* Review C-Section decision patterns to reduce unnecessary surgical delivery.

* Integrate psychosocial stress assessment into standard prenatal intake.

---

## **9. Limitations**

* High data attrition due to removal of "UNKNOWN" entries.

* Self-reported birth outcome data.

* Income midpoint conversion introduces approximation.

* No comparison with post-pandemic cohort.

---

## **Conclusion**

This project presents a structured, interactive analysis of maternal mental health and neonatal outcomes during COVID-19 using dashboard-based segmentation.

The analysis highlights:

* Elevated anxiety and stress levels

* Higher-than-baseline preterm rates

* Demographic and socioeconomic variation in outcomes

The Google Sheets dashboard enables dynamic exploration of these patterns and supports data-informed maternal healthcare decision-making.



