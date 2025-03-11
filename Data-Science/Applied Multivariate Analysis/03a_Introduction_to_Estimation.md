# Estimation, Hypothesis Testing and Anova

## **Normal Univariate Distribution**

### **1. Normal Distribution**
The **normal distribution** is one of the most important probability distributions in statistics. It describes a continuous random variable whose values are symmetrically distributed around the mean, forming the classic bell-shaped curve.

#### **Formula of the Normal Distribution**
The probability density function (PDF) of a normal distribution is defined as:
$$
f(x) = \frac{1}{\sqrt{2\pi\sigma^2}} \, e^{-\frac{(x-\mu)^2}{2\sigma^2}}
$$
Where:
- \(x\): The value of the random variable
- \(\mu\): Mean (center of the distribution)
- \(\sigma\): Standard deviation (spread or variability)
- \(\sigma^2\): Variance

This formula calculates the probability density at a specific value \(x\), showing how the likelihood changes across the curve.

---

### **2. Two Parameters: Mean and Standard Deviation**
The normal distribution is determined by two parameters:
1. **Mean (\(\mu\)):**
   - Determines the central location of the curve. Changing the mean shifts the curve along the x-axis.
   - Example: \(\mu = 0\) centers the curve at 0.

2. **Standard Deviation (\(\sigma\)):**
   - Determines the spread of the curve. Larger \(\sigma\) values result in wider, flatter curves, while smaller \(\sigma\) values lead to narrower, taller curves.

Together, these parameters shape the **location** and **spread** of the distribution.

---

### **3. Standard Normal \(Z\) Distribution**
The **standard normal distribution** is a special case of the normal distribution with:
- **Mean (\(\mu\)) = 0**
- **Standard Deviation (\(\sigma\)) = 1**

It is used to standardize normal distributions, allowing comparisons between datasets. The standard normal distribution is symmetric around \(z = 0\).

#### **Key Properties:**
- **Values Left of Center Are Negative:** For \(z < 0\), values are on the left side.
- **Values Right of Center Are Positive:** For \(z > 0\), values are on the right side.
- **Total Area Under the Curve = 1:** The curve represents a probability density function, so the entire area sums to 1.
- **Equal Area on Both Sides:** The distribution is symmetric, with 50% of the area on either side of the mean (\(z = 0\)).

#### **Z-Score:**
The z-score represents the number of standard deviations a value \(x\) is from the mean:
$$
z = \frac{x - \mu}{\sigma}
$$

---

### **4. Method of Probability Calculation**
To calculate probabilities for a standard normal distribution, you use areas under the curve. These probabilities are determined using **z-tables** or statistical software.

#### **Example: \(P(0 < z < K)\)**
The probability that \(z\) falls between 0 and \(K\) is calculated as:
$$
P(0 < z < K) = P(z < K) - P(z < 0)
$$
Where:
- \(P(z < K)\): Cumulative probability up to \(K\).
- \(P(z < 0)\): Cumulative probability up to 0 (which is always 0.5 due to symmetry).

---

This structured explanation covers the essentials of the **normal univariate distribution** and its associated calculations. Let me know if you’d like more clarification or examples!

### **Unimodal Data Pattern**

A **unimodal** data pattern refers to a dataset that has a **single peak** in its frequency distribution. This means the data is concentrated around one predominant value, and the distribution has one distinct mode (the most frequently occurring value). Unimodal data is commonly found in natural phenomena and often serves as the foundation for various statistical analyses.

---

#### **1. Central Tendency**
The **central tendency** of unimodal data refers to the central value around which the data is clustered. The measures of central tendency include:
- **Mean:** The arithmetic average, which is the most common measure for symmetric unimodal distributions.
- **Median:** The middle value when the data is ordered. In unimodal distributions, it is robust against outliers and skewness.
- **Mode:** The most frequently occurring value. For unimodal data, the mode corresponds to the peak of the distribution.

**Key Insight:**
For a perfectly symmetrical unimodal distribution (like a normal distribution), the mean, median, and mode are equal.

---

#### **2. Variation**
**Variation** describes the spread or dispersion of data around the central value in a unimodal distribution. Common measures of variation include:
- **Range:** Difference between the maximum and minimum values. It provides a simple measure of data spread.
- **Variance:** Represents the average squared deviation of data points from the mean, indicating overall dispersion.
- **Standard Deviation:** The square root of variance, which quantifies the spread in the same units as the data.
- **Interquartile Range (IQR):** The spread of the middle 50% of the data, making it robust to outliers.

**Key Insight:**
In unimodal distributions, smaller variation suggests a more peaked and concentrated pattern, while larger variation indicates a flatter spread.

---

#### **3. Shape**
The **shape** of unimodal data provides insights into the symmetry, skewness, and tailedness of the distribution.

##### **Symmetry:**
- **Symmetrical:** A perfectly balanced unimodal distribution (e.g., normal distribution) has equal spread on both sides of the peak.
- **Skewed:** The distribution may lean to one side.
  - **Positively Skewed (Right-Skewed):** Long tail extends to the right.
  - **Negatively Skewed (Left-Skewed):** Long tail extends to the left.

##### **Tailedness (Kurtosis):**
- **Leptokurtic:** A unimodal distribution with sharp peak and heavy tails.
- **Mesokurtic:** Moderate peak and tail behavior, as seen in a normal distribution.
- **Platykurtic:** Flatter peak with light tails.

---

A **unimodal data pattern** allows for easier interpretation of central tendencies, variability, and symmetry, making it a foundational concept in statistics. 

---




