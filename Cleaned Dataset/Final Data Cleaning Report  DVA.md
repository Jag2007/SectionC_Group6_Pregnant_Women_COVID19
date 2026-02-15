## Data  Cleaning  Documentation

---

### **1\. Column: OSF\_ID**

1. **Initial Data Type:** Numeric (ID column)  
2. **Kept or Dropped:** Dropped  
3. **Reason:** Not useful for analysis or visualization; only a serial identifier  
4. **Null Values Before Cleaning:** 0  
5. **Null Handling Method:** Not required  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** N/A  
8. **Reason for Method:** Column does not contribute to insights, prediction, or dashboard metrics  
9. **Outliers Present:** No**Data Transformation:** None  
10. **Final Status:** Column removed from dataset

---

### **2\. Column: Maternal\_Age**

1. **Initial Data Type:** Numeric (Continuous)  
2. **Kept or Dropped:** Kept  
3. **Reason:** Important feature for pregnancy risk analysis and dashboard insights , it indicated Maternal Age (years) at intake  
4. **Null Values Before Cleaning:** 1.12%  
5. **Null Handling Method:** Filled with Median  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** Median value of column  
8. **Reason for Method:** Median is less sensitive to outliers and provides a robust central value  
9. **Outliers Present:** Possible but handled via median imputation  
10. **Data Transformation:** Missing values replaced with median  
11. **Final Data Type:** Numeric

---

### **3\. Column: Household\_Income**

1. **Initial Data Type:** Categorical (income ranges)  
2. **Kept or Dropped:** Kept  
3. **Reason:** Important socioeconomic factors influencing pregnancy risk it shows us .This column shows the total household income of all family members combined from all sources (before taxes and deductions) for the year 2019\.  
4. **Null Values Before Cleaning:** 2.51%  
5. **Null Handling Method:** Converted ranges into numeric values  
6. **Null Values After Cleaning:** 0  
7. **Transformation Applied:**  
   * Converted income ranges into numeric midpoint values  
   * Examples:  
     * $20k–$39k → 30000  
     * $40k–$69k → 55000  
     * $70k–$99k → 85000  
     * $100k–$124k → 112500  
     * $200k+ → 200000  
8. **Reason for Method:** Numeric format required for analysis and dashboard metrics; midpoint provides realistic representation  
9. **Outliers Present:** High-income values retained as valid indicators  
10. **Final Data Type:** Numeric

---

### **4\. Column: Maternal\_Education**

1. **Initial Data Type:** Categorical  
2. **Kept or Dropped:** Kept  
3. **Reason** : This column indicates the education level of the mother, ranging from less than high school to doctoral degree.  
4. **Null Values Before Cleaning:** 1.77%  
5. **Null Handling Method:**  
   * Mode imputation attempted but not possible due to equal frequency of categories  
   * Missing values filled with "UNKNOWN"  
   * Rows containing "UNKNOWN" were dropped  
6. **Reason:** No dominant category existed; mode filling would introduce bias  
7. **Null Values After Cleaning:** 0  
8. **Outliers Present:** Not applicable (categorical data)  
9. **Final Data Type:** Categorical (cleaned)

---

### **5\. Column: EPDS (Edinburgh Postnatal Depression Scale)**

1. **Initial Data Type:** Numeric  
2. **Kept or Dropped:** Kept  
3. **Reason:** Primary clinical outcome measuring maternal depression severity. This column indicates the level of postnatal depression symptoms in mothers, where higher scores reflect greater depression severity.  
4. **Null Values Before Cleaning:** 11.74%  
5. **Null Handling Method:** Filled with Median  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** Median  
8. **Reason for Method:** Median preserves central tendency and reduces distortion from skew or extreme values  
9. **Outliers Present:** Yes  
10. **Data Transformation:** None  
11. **Final Data Type:** Numeric

---

### **6\. Column: PROMIS\_Anxiety**

1. **Initial Data Type:** Numeric  
2. **Kept or Dropped:** Kept  
3. **Reason:** Primary clinical outcome measuring maternal anxiety severity. This column shows the severity of maternal anxiety on a scale from 7 to 35, with higher scores indicating higher anxiety levels.  
4. **Null Values Before Cleaning:** 12.06%  
5. **Null Handling Method:** Filled with Median  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** Median  
8. **Reason for Method:** Median preserves distribution and avoids distortion from extreme values  
9. **Outliers Present:** Yes  
10. **Data Transformation:** None  
11. **Final Data Type:** Numeric

---

## **7\. Column: GAbirth (Gestational Age at Birth)**

1. **Initial Data Type:** Numeric  
2. **Kept or Dropped:** Kept  
3. **Reason:** Important clinical indicator related to pregnancy duration and birth outcomes. This column indicates the gestational age of the baby at birth measured in weeks.  
4. **Null Values Before Cleaning:** 40.38%  
5. **Null Handling Method:** Filled with "UNKNOWN" and rows with UNKNOWN removed  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** UNKNOWN (temporary)  
8. **Reason for Method:** High missing percentage (\>40%) would bias data if filled with mean/median; removing unknown rows ensured reliable dataset  
9. **Outliers Present:** Yes  
10. **Data Transformation:** None  
11. **Final Data Type:** Numeric

---

## **8\. Column: Birth\_Length**

1. **Initial Data Type:** Numeric  
2. **Kept or Dropped:** Kept  
3. **Reason:** Important indicator for identifying premature birth and neonatal health. This column indicates the baby’s birth length measured in centimeters.  
4. **Null Values Before Cleaning:** 40%  
5. **Null Handling Method:** Filled with "UNKNOWN" and rows with UNKNOWN removed  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** UNKNOWN (temporary)  
8. **Reason for Method:** High null percentage could bias results if filled with mean/median; removing unknown ensured data accuracy  
9. **Outliers Present:** Yes  
10. **Data Transformation:** None  
11. **Final Data Type:** Numeric

---

## **9\. Column: Birth\_Weight**

1. **Initial Data Type:** Numeric  
2. **Kept or Dropped:** Kept  
3. **Reason:** Strong indicator of baby health and birth outcomes. This column shows the baby’s birth weight measured in grams.  
4. **Null Values Before Cleaning:** 52%  
5. **Null Handling Method:** Filled with "UNKNOWN" and rows with UNKNOWN removed  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** UNKNOWN (temporary)  
8. **Reason for Method:** More than half data missing; filling with mean/median would heavily bias results, so invalid rows were removed  
9. **Outliers Present:** Yes  
10. **Data Transformation:** None  
11. **Final Data Type:** Numeric

---

## **10\. Column: Delivery\_Mode**

1. **Initial Data Type:** Categorical (Text)  
2. **Kept or Dropped:** Kept  
3. **Reason:** Important delivery outcome indicator.  This column indicates the method of delivery, whether vaginal delivery or caesarean section (C-section).  
4. **Null Values Before Cleaning:** 46%  
5. **Null Handling Method:** Filled with "UNKNOWN" and rows with UNKNOWN removed  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** UNKNOWN (temporary)  
8. **Reason for Method:** Mode filling would bias dataset due to limited categories; dropping unknown ensured data reliability  
9. **Outliers Present:** No  
10. **Data Transformation:** None  
11. **Final Data Type:** Categorical (Text)

---

## **11\. Column: Delivery\_Date**

1. **Initial Data Type:** Text (Date)  
2. **Kept or Dropped:** Dropped  
3. **Reason:** High percentage of missing values (\~40%) and not required for dashboard analysis.This column shows the delivery date of the baby, converted into month and year format.  
4. **Null Values Before Cleaning:** 40%  
5. **Null Handling Method:** Not applicable (column removed)  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** N/A  
8. **Reason for Method:** Column not relevant for analysis and contained excessive missing values  
9. **Outliers Present:** No  
10. **Data Transformation:** None  
11. **Final Status:** Column removed from dataset

---

## **12\. Column: NICU\_Stay**

1. **Initial Data Type:** Boolean  
2. **Kept or Dropped:** Kept  
3. **Reason:** Indicates whether the newborn required NICU stay, an important indicator of baby health.This column shows whether the newborn was admitted to the Neonatal Intensive Care Unit (NICU) after birth.  
4. **Null Values Before Cleaning:** 52.38%  
5. **Null Handling Method:** Filled with "UNKNOWN" and rows with UNKNOWN removed  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** UNKNOWN (temporary)  
8. **Reason for Method:** More than 50% data missing; filling with mode would bias results, so invalid rows were removed  
9. **Outliers Present:** No (categorical/boolean column)  
10. **Data Transformation:** None  
11. **Final Data Type:** Boolean

---

## **13\. Column: Language**

1. **Initial Data Type:** Text  
2. **Kept or Dropped:** Dropped  
3. **Reason:** Majority of responses were from one language group; not required for risk analysis and could bias overall averages.This column indicates the language in which the survey was completed.  
4. **Null Values Before Cleaning:** 2 cells  
5. **Null Handling Method:** Not applicable (column removed)  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** N/A  
8. **Reason for Method:** Column not relevant for analysis and removed to avoid biased interpretation  
9. **Outliers Present:** No  
10. **Data Transformation:** None  
11. **Final Status:** Column removed from dataset

---

## **14\. Column: Threaten\_Life**

1. **Initial Data Type:** Numeric  
2. **Kept or Dropped:** Kept  
3. **Reason:** How much do (did) you think your life is (was) in danger during the COVID-19 pandemic? (0-100).This column shows how much the mother felt her life was in danger during the COVID-19 pandemic, measured on a scale from 0 to 100\.  
4. **Null Values Before Cleaning:** 8.96%  
5. **Null Handling Method:** Filled with Median  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** Median  
8. **Reason for Method:** Numeric stress score with outliers; median is robust and less affected by extreme values  
9. **Outliers Present:** Yes  
10. **Data Transformation:** None  
11. **Final Data Type:** Numeric

---

## **15\. Column: Threaten\_Baby\_Danger**

1. **Initial Data Type:** Numeric  
2. **Kept or Dropped:** Kept  
3. **Reason:**  How much do (did) you think your unborn baby's life is (was) in danger at any time during the COVID-19 pandemic? (0-100).This column indicates the mother’s perception of how much her unborn baby’s life was in danger during the COVID-19 pandemic, measured on a scale from 0 to 10  
4. **Null Values Before Cleaning:** 9.04%  
5. **Null Handling Method:** Filled with Median  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** Median  
8. **Reason for Method:** Numeric stress-related score; median handles missing values without bias from outliers  
9. **Outliers Present:** Yes  
10. **Data Transformation:** None  
11. **Final Data Type:** Numeric

---

## **16\. Column: Threaten\_Baby\_Harm**

1. **Initial Data Type:** Numeric  
2. **Kept or Dropped:** Kept  
3. **Reason:** How much are you worried that exposure to the COVID-19 virus will harm your unborn baby? (0-100).This column shows the level of concern the mother had that exposure to COVID-19 could harm her unborn baby, measured on a scale from 0 to 100\.  
4. **Null Values Before Cleaning:** 8.92%  
5. **Null Handling Method:** Filled with Median  
6. **Null Values After Cleaning:** 0  
7. **Filled With:** Median  
8. **Reason for Method:** Numeric column with outliers; median ensures robust imputation  
9. **Outliers Present:** Yes  
10. **Data Transformation:** None  
11. **Final Data Type:** Numeric

---

## **17\. Column: Maternal\_Pandemic\_Stress**

1. **Column Type:** Derived / Calculated  
2. **Created From:** Threaten\_Life, Threaten\_Baby\_Danger, Threaten\_Baby\_Harm  
3. **Formula Used:**  
   (0.3 × Threaten\_Life) \+ (0.35 × Threaten\_Baby\_Danger) \+ (0.35 × Threaten\_Baby\_Harm)  
4. **Purpose:** To combine multiple maternal stress indicators into a single overall stress score for easier analysis and dashboard visualization  
5. **Final Data Type:** Numeric

---

## **18\. Column: Conceive\_Age**

1. **Column Type:** Calculated / Derived Column  
2. **Created From:** Maternal\_Age and Gestational\_Age\_At\_Birth  
3. **Formula Used:** `ROUND(Maternal_Age − (Gestational_Age_At_Birth/52))`  
4. **Purpose:** To estimate the mother’s age at the time of conception by adjusting maternal age with gestational duration  
5. **Reason for Creation:** Helps in understanding maternal age at conception for better demographic and clinical insights  
6. **Final Data Type:** Numeric

---

## **19\. Column: Threat\_Severity**

1. **Column Type:** Calculated / Derived Column  
2. **Created From:** Maternal\_Pandemic\_Stress  
3. **Formula Used:** `IF(N2="","",IF(N2<=30,"Low",IF(N2<=70,"Medium","High")))`  
4. **Purpose:** This column categorizes the overall maternal pandemic stress score into Low, Medium, or High severity levels to simplify interpretation and enable easier comparison in dashboard visualizations.  
5. **Reason for Creation:** Converting numeric stress scores into severity categories helps in identifying high-risk groups and improves readability of insights.  
6. **Final Data Type:** Text (Categorical)

---

## **20\. Column: Preterm**

1. **Column Type:** Calculated / Derived Column  
2. **Created From:** Gestational\_Age\_At\_Birth  
3. **Formula Used:** `IF(Gestational_Age_At_Birth<37,"Preterm","Full Term")`  
4. **Purpose:** This column identifies whether the baby was born preterm or full term based on gestational age, which is a key indicator of neonatal health and pregnancy outcomes.  
5. **Reason for Creation:** Helps in analyzing birth outcomes and understanding the relationship between maternal stress and premature births.  
6. **Final Data Type:** Text (Categorical

---

**21\. Column: Depression\_Severity**

1. **Initial Data Type**: Categorical (Text)  
2. **Kept or Dropped**: Kept  
3. **Reason**: Indicates severity level of maternal depression (Minimal, Moderate, Severe) and supports mental health risk analysis.  
4. **Outliers Present**: Not applicable  
5. **Data Transformation**: Severity categories retained as provided  
6. **Final Data Type**: Categorical (Text)

---

**22\. Column: Maternal\_Age\_Group**

1. **Initial Data Type**: Categorical (Text)  
2. **Kept or Dropped**: Kept  
3. **Reason**: Categorizes mothers into Young, Adult, and High Risk groups for segmentation and dashboard insights.  
4. **Outliers Present**: Not applicable  
5. **Data Transformation**: Age groups retained for segmentation  
6. **Final Data Type**: Categorical (Text)

---

**23\. Column: Income\_Group**

1. **Initial Data Type:** Categorical (Text)  
2. **Kept or Dropped:** Kept  
3. **Reason:** Categorizes household income into Low, Middle, and High groups, helping analyze socioeconomic impact on maternal health, stress levels, and pregnancy outcomes.  
4. **Data Transformation:** Income categories retained as provided for segmentation and dashboard insights  
5. **Final Data Type:** Categorical (Text)

**Number of Columns Dropped : 3** 

**Number of Columns Added based on Analysis : 7**

