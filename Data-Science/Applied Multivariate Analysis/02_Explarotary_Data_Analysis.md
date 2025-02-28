# Exploratory Data Analysis (EDA)

## Introduction 
Exploratory Data Analysis (EDA) is the process of analyzing datasets to summarize their key characteristics, detect patterns, identify anomalies, and check assumptions before applying machine learning models or statistical methods. It involves both graphical and numerical techniques to understand the structure and relationships within the data.  

EDA is often the first step in data analysis and helps in making informed decisions on how to clean, transform, and model the data.  

Key techniques in EDA include:  
- **Summary statistics** – Mean, median, standard deviation, percentiles, etc.  
- **Data visualization** – Histograms, box plots, scatter plots, correlation matrices, etc.  
- **Handling missing values** – Identifying and deciding whether to remove or impute missing data.  
- **Outlier detection** – Identifying data points that deviate significantly from the majority.  

---

### Why EDA is important?
EDA is crucial because it ensures that data is well understood before applying statistical models or machine learning algorithms. It helps in:  

### **1. Understanding Data Structure**  
EDA helps uncover data distributions, relationships between variables, and possible errors, ensuring that the dataset is suitable for analysis.  

### **2. Identifying Data Quality Issues**  
It reveals missing values, duplicate records, inconsistencies, and outliers, allowing for data cleaning and preprocessing to improve model performance.  

### **3. Detecting Patterns and Relationships**  
Visualizations and summary statistics help recognize correlations, clusters, and trends that can guide feature selection and engineering.  

### **4. Avoiding Incorrect Assumptions**  
EDA validates assumptions about the data, such as normality, linearity, or independence, which are critical for statistical models and machine learning algorithms.  

### **5. Guiding Model Selection**  
Understanding the data helps in choosing appropriate algorithms, tuning hyperparameters, and preventing overfitting or underfitting.  

## How Data is Measured?
The way data is measured depends heavily on the type of data being collected. However, we can break down data measurement into a few core concepts:

### **1. Scales of Measurement:**

These scales determine the type of information a variable provides and the statistical analyses that can be performed. There are four primary scales:

* **Nominal Scale:**
    * This is the most basic level. Data is categorized into distinct groups with no inherent order.
    * Examples: Colors, genders, types of animals.
* **Ordinal Scale:**
    * Data is categorized and ranked, meaning there's a meaningful order. However, the intervals between values aren't necessarily equal.
    * Examples: Satisfaction ratings (e.g., very dissatisfied, dissatisfied, neutral, satisfied, very satisfied), education levels (e.g., high school, bachelor's, master's).
* **Interval Scale:**
    * Data is ranked, and the intervals between values are equal. However, there's no true zero point.
    * Examples: Temperature in Celsius or Fahrenheit.
* **Ratio Scale:**
    * This is the highest level of measurement. Data is ranked, intervals are equal, and there's a true zero point, meaning ratios are meaningful.
    * Examples: Height, weight, age, income.

### **2. Units of Measurement:**

* For quantitative data (interval and ratio scales), specific units are used to quantify the data.
    * Examples: Meters for length, kilograms for weight, seconds for time.
* In the digital realm, data is measured in bits and bytes, with larger units like kilobytes, megabytes, gigabytes, and terabytes.

### **3. Data Quality:**

Beyond the scales and units, data measurement also involves assessing data quality. Key aspects include:

* **Accuracy:** How close the measured value is to the true value.
* **Completeness:** Whether all required data is present.
* **Consistency:** Whether data is formatted and stored in a uniform way.
* **Timeliness:** Whether data is available when needed.
* **Validity:** Whether data measures what it's intended to measure.

## Summarizing by Types of Variables
When performing Exploratory Data Analysis (EDA), it's crucial to understand the different types of variables you're working with. Two fundamental categories are:

### **1. Categorical Variables:**

* **Definition:**
    * Categorical variables represent qualities or characteristics. They divide data into distinct groups or categories.
    * These variables typically answer "what type?" or "which category?" questions.
* **Types:**
    * **Nominal:** Categories have no inherent order (e.g., colors, genders, types of fruit).
    * **Ordinal:** Categories have a meaningful order or ranking (e.g., education levels, customer satisfaction ratings).
* **EDA Techniques:**
    * Frequency tables: Show the distribution of categories.
    * Relative Frequency tables: Show the percent in each categories.
    * Bar charts: Visually represent the frequency of categories.
    * Pie charts: Show the proportion of each category.
    * Chi-squared tests: used to examine the relationship between two categorical variables.

### **2. Continuous Variables:**

* **Definition:**
    * Continuous variables represent measurable quantities that can take on any value within a range.
    * These variables typically answer "how much?" or "how many?" questions.
* **Characteristics:**
    * Can take on an infinite number of values within a given range.
    * Often measured with decimals.
* **Examples:**
    * Height, weight, temperature, time, income.
* **EDA Techniques:**
    * Histograms: Show the distribution of values.
    * Box plots: Display the median, quartiles, and outliers.
    * Scatter plots: Visualize the relationship between two continuous variables.
    * Descriptive statistics (mean, median, standard deviation): Summarize the central tendency and spread of the data.
    * Correlation matrixes: used to show the correlation between multiple continuous variables.

**Key Differences Summarized:**

* **Nature of Data:** Categorical variables deal with categories, while continuous variables deal with numerical measurements.
* **Values:** Categorical variables have a limited number of distinct values, while continuous variables can have an infinite number of values within a range.
* **Analysis:** Different statistical and visualization techniques are used for each type of variable.

The goal for both categorical and continuous data is data
reduction while preserving/extracting key information
about the process under investigation.

## Univariate Analysis in EDA

Univariate analysis is a type of exploratory data analysis (EDA) that focuses on analyzing a single variable (or feature) at a time. The goal is to understand the distribution, central tendency, dispersion, and shape of the data.

"Uni" means one, so univariate analysis does not consider relationships between multiple variables—only the properties of one variable at a time.

### Purpose of Univariate Analysis
- Helps identify patterns within a single variable.
- Detects data issues like outliers and missing values.
- Guides data preprocessing and transformations before modeling.
- Assesses assumptions for statistical methods (e.g., normality, skewness).

### **Categories of Univariate Analysis**  

Univariate analysis is categorized into several statistical measures:  

#### **1. Measures of Location (Central Tendency)**  
These describe where the data is centered or typical values in the dataset.  
- **Mean (Average):** The sum of all values divided by the number of observations.  
- **Median:** The middle value when data is sorted in ascending order (robust to outliers).  
- **Mode:** The most frequently occurring value(s) in the dataset.  

📌 *Example:* If a dataset contains students' test scores:  
- Mean = 75  
- Median = 78  
- Mode = 80 (if 80 appears most often)  

#### **2. Measures of Variability (Dispersion)**  
These show how spread out the data is.  
- **Range:** Difference between the maximum and minimum values.  
- **Variance:** The average squared difference from the mean.  
- **Standard Deviation (SD):** The square root of variance, indicating data spread in the same unit as the original variable.  
- **Interquartile Range (IQR):** The range between the 25th percentile (Q1) and 75th percentile (Q3), useful for detecting outliers.  

📌 *Example:* If test scores range from 50 to 100, the range = 50. If SD = 10, most students' scores lie within ±10 of the mean.  

#### **3. Measures of Heterogeneity**  
These measure diversity or differences in a dataset.  
- **Coefficient of Variation (CV):** Standard deviation divided by the mean (relative measure of dispersion).  
- **Entropy:** A measure of randomness or unpredictability in the data.  

📌 *Example:* If two datasets have the same mean but different SDs, CV helps compare their variability.  

#### **4. Measures of Concentration**  
These assess how data points are distributed in a given range.  
- **Gini Index:** Measures inequality in distribution (commonly used in economics).  
- **Herfindahl Index:** Measures market concentration (used in competition analysis).  

📌 *Example:* A dataset with similar values will have a lower Gini Index, while one with extreme differences will have a higher Gini Index.  

#### **5. Measures of Asymmetry (Skewness)**  
Skewness measures whether data is symmetric or skewed toward one side.  
- **Positive skew:** Tail on the right (mean > median).  
- **Negative skew:** Tail on the left (mean < median).  
- **Zero skew:** Perfectly symmetrical distribution.  

📌 *Example:*  
- Income distribution is usually **right-skewed** (a few people earn very high salaries).  
- Heights of people are usually **normally distributed** (zero skew).  

#### **6. Measures of Kurtosis**  
Kurtosis measures whether a dataset has heavy or light tails compared to a normal distribution.  
- **Mesokurtic (kurtosis = 3):** Normal distribution.  
- **Leptokurtic (kurtosis > 3):** More extreme outliers (heavy tails).  
- **Platykurtic (kurtosis < 3):** Fewer outliers (light tails).  

📌 *Example:* Stock market returns often have **leptokurtic** distributions because of occasional extreme gains or losses.  

---

### **EDA Techniques**  
To perform univariate analysis in EDA, we use:  

1. **Descriptive statistics** – Mean, median, SD, skewness, kurtosis.  
2. **Visualizations** – Histograms, box plots, density plots.  
3. **Outlier detection** – Using IQR and standard deviation.  

By analyzing each variable separately, univariate EDA provides essential insights into the dataset before exploring relationships between multiple variables.

### **Numerical Data Properties**  

### **1. Central Tendency (Location)**  
Central tendency measures where most of the data values are located. It gives a single representative value for the dataset.  

📌 **Common Measures:**  
- **Mean (Average):**  
  \[
  \text{Mean} = \frac{\sum X}{N}
  \]  
  The sum of all values divided by the number of observations. Sensitive to outliers. 
  - **Properties :**
    - Measure of Central Tendency
    - Most Common Measure
    - Acts as 'Balance Point' 
    - Affected by Ectreme Values ('Outliers')
- **Median:** The middle value when data is sorted. More robust to outliers.  
  - **Properties :**
    - Measure of Central Tendency
    - Middle Value in Ordered Sequence
      - If Odd n, Middle Value of Sequence
      - If Even n, Average of 2 Middle Values
    - Not Affected by Ectreme Values ('Outliers')
- **Mode:** The most frequently occurring value(s). Useful for categorical and numerical data.  
  - **Properties :**
    - Measure of Central Tendency
    - Value that occurs most often
    - May be no mode or several modes
    - May be used for numerical and categorical data.
      - If Odd n, Middle Value of Sequence
      - If Even n, Average of 2 Middle Values
    - Not Affected by Ectreme Values ('Outliers')

📌 **Example:** Exam scores = **[70, 75, 80, 85, 90]**  
- Mean = **80**  
- Median = **80**  
- Mode = **None (no repeating values)**  

---

### **2. Variation (Dispersion)**  
Variation measures how spread out the data points are. It helps in understanding consistency and detecting outliers.  

📌 **Common Measures:**  
- **Range:**  
  \[
  \text{Range} = \text{Max} - \text{Min}
  \]  
  The simplest measure of spread, but highly affected by outliers.  
- **Variance (σ²):**  
  \[
  \sigma^2 = \frac{\sum (X - \bar{X})^2}{N}
  \]  
  The average squared difference from the mean.  
- **Standard Deviation (σ):**  
  \[
  \sigma = \sqrt{\sigma^2}
  \]  
  Measures spread in the same unit as the data.  
- **Interquartile Range (IQR):**  
  \[
  IQR = Q3 - Q1
  \]  
  The difference between the 75th percentile (Q3) and 25th percentile (Q1), useful for detecting outliers.  

📌 **Example:** Exam scores = **[50, 60, 70, 80, 90]**  
- Range = **90 - 50 = 40**  
- Standard Deviation ≈ **14.14**  

---

### **3. Shape**  
Shape describes the distribution pattern of the data. It helps in identifying skewness, symmetry, and the presence of extreme values.  

📌 **Common Measures:**  
- **Skewness (Asymmetry in Data Distribution)**  
  - **Positive skew (Right-skewed):** Mean > Median, longer right tail.  
  - **Negative skew (Left-skewed):** Mean < Median, longer left tail.  
  - **Zero skew (Symmetric):** Mean = Median.  
- **Kurtosis (Tail Heaviness of Distribution)**  
  - **Mesokurtic (Normal, kurtosis ≈ 3)** – Standard bell curve.  
  - **Leptokurtic (Heavy tails, kurtosis > 3)** – More extreme outliers.  
  - **Platykurtic (Light tails, kurtosis < 3)** – Fewer extreme values.  

📌 **Example:** Income distribution is usually **right-skewed**, with a few very high incomes pulling the mean higher than the median.  

---

### **Summary Table**  

| Property  | Definition | Common Measures |  
|-----------|-------------|------------------|  
| **Central Tendency** | Where the data is centered | Mean, Median, Mode |  
| **Variation** | How spread out the data is | Range, Variance, Standard Deviation, IQR |  
| **Shape** | The pattern of distribution | Skewness, Kurtosis |  

Understanding these numerical properties in EDA helps in selecting the right preprocessing techniques and modeling approaches. 🚀


