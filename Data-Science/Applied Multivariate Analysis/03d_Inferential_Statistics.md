# **Inferential Statistics (Normal Univariate)**

## **Involves**
1. **Estimation**:
   - Includes **point estimation** (e.g., sample mean or variance) and **interval estimation** (e.g., confidence intervals).
   - Used to estimate population parameters based on sample data.

2. **Hypothesis Testing**:
   - Aims to test assumptions about population parameters using sample evidence.
   - Example: Testing whether the population mean equals a specific value.

---

## **Purpose**
- The primary goal is to **make decisions** or draw conclusions about **population characteristics** based on a sample.
- Helps quantify uncertainty in conclusions, ensuring decisions are statistically sound.

## **Key Terms**

### **Population (P)**
- The entire group of individuals or items that we want to study or make inferences about.
- Examples:
  - All adults in a city.
  - Every manufactured product in a factory.

### **Sample (S)**
- A subset of the population selected for study.
- The sample is used to draw conclusions about the population.
- Examples:
  - A group of 100 individuals surveyed from a city.
  - 50 randomly selected products from a production line.

### **Parameter**
- A numerical value that describes a characteristic of the population.
- Parameters are typically unknown and require estimation.
- Examples:
  - Population mean (\( \mu \)).
  - Population variance (\( \sigma^2 \)).

### **Statistics**
- A numerical value that describes a characteristic of the sample.
- Statistics are calculated from sample data and used to estimate parameters.
- Examples:
  - Sample mean (\( \bar{X} \)).
  - Sample variance (\( s^2 \)).


## **Formulating Hypothesis**

### **1. Null Hypothesis (\(H_0\))**
- The **null hypothesis** represents the default assumption or claim about a population parameter. It is often a statement of "no effect," "no difference," or "status quo."
- Examples:
  - \(H_0: \mu = \mu_0\) (The population mean equals a specified value \(\mu_0\)).
  - \(H_0: p = p_0\) (The population proportion equals \(p_0\)).
  - \(H_0: \sigma_1^2 = \sigma_2^2\) (The variances of two populations are equal).

---

### **2. Alternative Hypothesis (\(H_1\) or \(H_a\))**
- The **alternative hypothesis** is a statement that contradicts the null hypothesis. It represents what the researcher wants to prove or the existence of an effect or difference.
- It is typically formulated as one of the following:
  - **One-Sided Test** (Directional):
    - \(H_a: \mu > \mu_0\) (The mean is greater than \(\mu_0\)).
    - \(H_a: \mu < \mu_0\) (The mean is less than \(\mu_0\)).
  - **Two-Sided Test** (Non-Directional):
    - \(H_a: \mu \neq \mu_0\) (The mean is not equal to \(\mu_0\)).

---

### **3. How to Reject \(H_0\)**

#### **Steps to Reject the Null Hypothesis**
1. **Set the Significance Level (\(\alpha\)):**
   - Determine the probability of making a Type I error (rejecting \(H_0\) when it is true).
   - Common values: \( \alpha = 0.05 \) (5% significance level) or \( \alpha = 0.01 \) (1% significance level).

2. **Choose the Appropriate Test Statistic:**
   - **Z-Test:** Used when population variance is known and sample size is large.
   - **T-Test:** Used when population variance is unknown and sample size is small.
   - **Chi-Square Test:** Used to test categorical data or variance.
   - **ANOVA:** Compares means across multiple groups.

3. **Calculate the Test Statistic:**
   - Example for \( Z \)-Test:
     $$
     Z = \frac{\bar{X} - \mu_0}{\frac{\sigma}{\sqrt{n}}}
     $$

4. **Determine the Critical Region:**
   - Identify the critical value(s) based on the significance level and the type of test (one-sided or two-sided).
   - **Critical Region**: The range of test statistic values that lead to rejecting \(H_0\).

5. **Compute the P-Value:**
   - The p-value represents the probability of obtaining a result as extreme as the observed value, assuming \(H_0\) is true.
   - If \( p \leq \alpha \), reject \(H_0\).

6. **Compare and Conclude:**
   - If the test statistic falls within the critical region or \( p \leq \alpha \), reject \(H_0\).
   - If the test statistic does not fall within the critical region or \( p > \alpha \), fail to reject \(H_0\).

---

### **Example**
#### Problem:
- Null Hypothesis (\(H_0\)): \( \mu = 100 \)
- Alternative Hypothesis (\(H_1\)): \( \mu > 100 \) (one-sided test).
- Sample Mean (\(\bar{X}\)) = 105, Population Standard Deviation (\(\sigma\)) = 15, Sample Size (\(n = 25\)).

#### Solution:
1. **Significance Level:** \( \alpha = 0.05 \).
2. **Test Statistic (Z):**
   $$
   Z = \frac{\bar{X} - \mu_0}{\frac{\sigma}{\sqrt{n}}} = \frac{105 - 100}{\frac{15}{\sqrt{25}}} = \frac{5}{3} = 1.67
   $$
3. **Critical Value:** For \( \alpha = 0.05 \), \( Z_{crit} = 1.645 \).
4. **Decision Rule:** Since \( Z = 1.67 > Z_{crit} = 1.645 \), 

## **Alternative Hypothesis**

### **Definition**
An **alternative hypothesis** (\(H_1\) or \(H_a\)) is a statement that reflects a researcher's claim or the existence of an effect, relationship, or difference in a population. It is directly tested against the **null hypothesis** (\(H_0\)), which assumes no effect or difference.

---

### **1. One-Tailed Alternative Hypothesis**

#### **Definition**
A **one-tailed test** considers deviations from the null hypothesis in only one direction. It is used when researchers expect the effect or difference to occur in a specific direction.

#### **Examples**
1. **Positive Direction**:
   - \(H_1: \mu > \mu_0\): The population mean is greater than a specific value (\(\mu_0\)).
   - Example: Testing whether a new fertilizer increases crop yield compared to the standard fertilizer.
2. **Negative Direction**:
   - \(H_1: \mu < \mu_0\): The population mean is less than a specific value (\(\mu_0\)).
   - Example: Testing whether a drug reduces blood pressure below a specific threshold.

---

### **2. Two-Tailed Alternative Hypothesis**

#### **Definition**
A **two-tailed test** considers deviations from the null hypothesis in both directions. It is used when researchers are interested in identifying any significant difference, regardless of direction.

#### **Example**
- \(H_1: \mu \neq \mu_0\): The population mean is different (either higher or lower) from a specific value (\(\mu_0\)).
- Example: Testing whether a new medication produces an effect, which could either increase or decrease blood pressure.

---

### **3. Essentials of Picking an Alternative Hypothesis**

#### **Factors to Consider**
1. **Nature of the Research Question**:
   - Use a **one-tailed hypothesis** if the effect is expected to occur only in one direction.
   - Use a **two-tailed hypothesis** if there is uncertainty or interest in any deviation from the null hypothesis.

2. **Practical Implications**:
   - A one-tailed test is more powerful for detecting a specific effect but risks missing a significant result in the opposite direction.
   - A two-tailed test is more conservative and ensures the results are evaluated in both directions.

3. **Significance Level (\(\alpha\))**:
   - In a one-tailed test, the entire significance level is allocated to one tail of the distribution (e.g., \( \alpha = 0.05 \)).
   - In a two-tailed test, the significance level is split between both tails (e.g., \( \alpha/2 = 0.025 \) in each tail for \( \alpha = 0.05 \)).

4. **Context of the Study**:
   - Consider the consequences of errors (Type I and Type II).
   - Use domain knowledge or prior research to guide the direction of the hypothesis.

#### **Examples of Application**:
- **One-Tailed Hypothesis**:
  - A company claims their product increases customer satisfaction scores above 90. Set \( H_1: \mu > 90 \).
- **Two-Tailed Hypothesis**:
  - A researcher is testing whether a training program affects test scores in any way. Set \( H_1: \mu \neq \mu_0 \) (where \( \mu_0 \) is the pre-training average).

---
## **Rejecting Hypothesis**

Rejecting a hypothesis involves determining whether there is enough evidence in the sample data to reject the **null hypothesis (\(H_0\))** in favor of the **alternative hypothesis (\(H_1\))**.

---

### **Steps to Reject a Hypothesis**

#### **1. Gather Data**
- **Definition**:
  - Collect and prepare the data necessary for hypothesis testing. Ensure the data is representative, properly measured, and relevant to the hypothesis being tested.
- **Types of Data**:
  - **Quantitative Data**: Continuous or discrete numerical data (e.g., weights, test scores).
  - **Qualitative Data**: Categorical data (e.g., gender, color).
- **Sampling**:
  - Use proper sampling techniques like random sampling to avoid bias.
  - Ensure sample size is adequate for reliable results (e.g., larger samples reduce variability).

---

#### **2. Use Statistical Test**
- **Definition**:
  - Perform an appropriate statistical test to determine whether to reject \(H_0\). The choice of the test depends on the nature of the data and the hypothesis.
- **Common Statistical Tests**:
  1. **Z-Test**:
     - Used when the population variance is known and the sample size is large.
     $$
     Z = \frac{\bar{X} - \mu_0}{\frac{\sigma}{\sqrt{n}}}
     $$
  2. **T-Test**:
     - Used when the population variance is unknown.
     $$
     T = \frac{\bar{X} - \mu_0}{\frac{s}{\sqrt{n}}}
     $$
  3. **Chi-Square Test**:
     - Used for categorical data or testing variances.
     $$
     \chi^2 = \sum \frac{(O_i - E_i)^2}{E_i}
     $$
  4. **ANOVA (Analysis of Variance)**:
     - Tests the differences among group means.
  5. **P-Test**:
     - Provides the probability of observing the test statistic as extreme as the one calculated.

---

#### **3. Use Statistics Table**
- **Definition**:
  - Compare the calculated test statistic to the critical value from a statistical distribution table to determine if the result falls within the rejection region.
- **Steps**:
  1. **Determine Degrees of Freedom (if required)**:
     - For the \(t\)-distribution or \( \chi^2 \)-distribution, calculate the degrees of freedom (df).
  2. **Find the Critical Value**:
     - Based on the significance level (\(\alpha\)) and the type of test (one-tailed or two-tailed), find the critical value from the statistics table.
  3. **Compare Test Statistic with Critical Value**:
     - **If Test Statistic > Critical Value** (or falls in the rejection region), reject \(H_0\).
     - Otherwise, fail to reject \(H_0\).

---

### **Example: One-Sample Z-Test**
1. **Hypothesis**:
   - \(H_0: \mu = 100\)
   - \(H_1: \mu > 100\) (one-tailed test)
2. **Sample Data**:
   - Sample mean (\(\bar{X}\)) = 105, Population Standard Deviation (\(\sigma\)) = 15, Sample Size (\(n = 25\)).
3. **Calculate the Test Statistic**:
   $$
   Z = \frac{\bar{X} - \mu_0}{\frac{\sigma}{\sqrt{n}}} = \frac{105 - 100}{\frac{15}{\sqrt{25}}} = 1.67
   $$
4. **Find Critical Value**:
   - From the Z-table for \(\alpha = 0.05\), \(Z_{crit} = 1.645\).
5. **Decision**:
   - Since \(Z = 1.67 > Z_{crit} = 1.645\), reject \(H_0\).

---

# **P-Value**

## **Definition**
The **p-value** (probability value) is a statistical measure that indicates the strength of evidence against the null hypothesis (\(H_0\)). It represents the probability of observing results as extreme as (or more extreme than) the actual observed data, assuming \(H_0\) is true.

---

## **Interpretation**
- A **small p-value** (\(p \leq \alpha\)) provides strong evidence to reject \(H_0\).
- A **large p-value** (\(p > \alpha\)) suggests insufficient evidence to reject \(H_0\).

### **Threshold (\(\alpha\))**
- The significance level (\(\alpha\)) is a threshold set by the researcher, typically 0.05 (5%) or 0.01 (1%).
  - **If \(p \leq \alpha\):** Reject \(H_0\) (result is statistically significant).
  - **If \(p > \alpha\):** Fail to reject \(H_0\) (result is not statistically significant).

---

## **Steps to Calculate P-Value**
1. **Formulate Hypotheses**:
   - Null Hypothesis (\(H_0\)): Represents the default assumption (e.g., \(H_0: \mu = \mu_0\)).
   - Alternative Hypothesis (\(H_1\)): Represents the claim being tested.

2. **Choose a Test Statistic**:
   - Example: \(Z\)-test for population mean, \(T\)-test for small samples, Chi-square test for categorical data.

3. **Compute the Test Statistic**:
   - Example for \(Z\)-test:
     $$
     Z = \frac{\bar{X} - \mu_0}{\frac{\sigma}{\sqrt{n}}}
     $$
     Where:
     - \(\bar{X}\): Sample mean.
     - \(\mu_0\): Population mean under \(H_0\).
     - \(\sigma\): Population standard deviation.
     - \(n\): Sample size.

4. **Determine the P-Value**:
   - The p-value corresponds to the area under the curve of the test statistic's probability distribution beyond the observed value.
   - For one-tailed tests, p-value is the area in one tail.
   - For two-tailed tests, p-value is the combined area in both tails.

---

## **Examples**

### **One-Tailed Test**
- Hypotheses:
  - \(H_0: \mu = 100\)
  - \(H_1: \mu > 100\)
- Sample Mean (\(\bar{X}\)) = 105, Population Standard Deviation (\(\sigma\)) = 15, Sample Size (\(n = 25\)).
- Test Statistic:
  $$
  Z = \frac{\bar{X} - \mu_0}{\frac{\sigma}{\sqrt{n}}} = \frac{105 - 100}{\frac{15}{\sqrt{25}}} = \frac{5}{3} = 1.67
  $$
- From the Z-table, \(p = 0.0475\).
- Decision:
  - At \(\alpha = 0.05\), \(p = 0.0475 \leq \alpha\), so reject \(H_0\).

---

### **Two-Tailed Test**
- Hypotheses:
  - \(H_0: \mu = 50\)
  - \(H_1: \mu \neq 50\)
- Sample Mean (\(\bar{X}\)) = 48, Sample Standard Deviation (\(s\)) = 5, Sample Size (\(n = 30\)).
- Test Statistic (\(T\)-test):
  $$
  T = \frac{\bar{X} - \mu_0}{\frac{s}{\sqrt{n}}} = \frac{48 - 50}{\frac{5}{\sqrt{30}}} = -2.19
  $$
- Degrees of Freedom (\(df\)) = \(n - 1 = 29\).
- From the T-table, \(p \approx 0.036\) (two-tailed).
- Decision:
  - At \(\alpha = 0.05\), \(p = 0.036 \leq \alpha\), so reject \(H_0\).

---

## **Key Points to Remember**
1. **P-value does NOT measure the probability that \(H_0\) is true.**
   - It only measures the likelihood of observing the data under \(H_0\).

2. **P-value depends on sample size**:
   - Larger samples can produce smaller p-values, even for small differences.

3. **Context Matters**:
   - Statistical significance (small p-value) does not always mean practical significance.

---

## **Applications**
- **Hypothesis Testing**:
  - In research studies, p-values guide the rejection of \(H_0\).
- **Model Evaluation**:
  - P-values are used in regression analysis to assess the significance of predictors.
- **Scientific Research**:
  - Used to validate experimental results across disciplines like medicine, psychology, and economics.

---

This note outlines the concept, calculation, and interpretation of the **p-value** in hypothesis testing.
