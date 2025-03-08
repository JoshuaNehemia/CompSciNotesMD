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

### **Normal Univariate: Point Estimation**

Point estimation refers to the process of estimating a population parameter (like the mean or mode) using sample data. Here’s an in-depth explanation of the requested concepts:

---

#### **1. Mean or Expected Value of a Random Variable \(X\)**
The **mean** or **expected value** represents the central or average value of a random variable. It is a measure of central tendency, providing the expected outcome of a random experiment.

##### **a. Formula for Discrete Random Variable**
For a discrete random variable \(X\) with possible values \(x_1, x_2, \dots, x_n\) and corresponding probabilities \(P(x_i)\), the expected value is calculated as:
$$
E(X) = \mu = \sum_{i=1}^{n} x_i P(x_i)
$$
Where:
- \(x_i\): Value of the random variable
- \(P(x_i)\): Probability of \(x_i\) occurring

##### **b. Formula for Continuous Random Variable**
For a continuous random variable \(X\) with probability density function \(f(x)\), the expected value is calculated as:
$$
E(X) = \mu = \int_{-\infty}^{\infty} x f(x) \, dx
$$
Where:
- \(f(x)\): PDF of the random variable \(X\)

---

#### **2. Mean Value of \(g(x, y)\)**
For a function \(g(x, y)\) involving two random variables \(X\) and \(Y\), the expected value of \(g(X, Y)\) is given by:
- **Discrete Variables:**
  $$
  E[g(X, Y)] = \sum_{x} \sum_{y} g(x, y) P(X = x, Y = y)
  $$
- **Continuous Variables:**
  $$
  E[g(X, Y)] = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} g(x, y) f(x, y) \, dx \, dy
  $$
Where:
- \(P(X = x, Y = y)\): Joint probability for discrete variables
- \(f(x, y)\): Joint probability density function for continuous variables

This concept is used to compute expected values for combinations or transformations of variables.

---

#### **3. Mode**
The **mode** is another measure of central tendency, representing the value that appears most frequently in a dataset or the peak in a probability distribution.

##### **Key Characteristics of the Mode:**
1. **Measure of Central Tendency:** It helps summarize data around the most frequent value.
2. **Value That Occurs Most Often:** The mode is the most common value in the dataset.
   - Example: For the dataset {2, 3, 3, 4}, the mode is 3.
3. **Not Affected by Extreme Values:** Unlike the mean, the mode is unaffected by outliers.
4. **May Be No Mode or Several Modes:** Datasets can be:
   - **Unimodal:** One mode (e.g., {2, 3, 3, 4}).
   - **Bimodal:** Two modes (e.g., {2, 3, 3, 4, 4}).
   - **Multimodal:** More than two modes.
   - **No Mode:** When all values occur with equal frequency.
5. **Applicable to Numerical and Categorical Data:**
   - Numerical: e.g., mode of test scores.
   - Categorical: e.g., mode of favorite colors.

---

### **Normal Univariate: Covariance and Variance Estimation**

---

#### **1. Variance of a Random Variable \(X\)**
Variance measures the spread or variability of a random variable \(X\) around its mean (\(\mu\)). It quantifies how much the values of \(X\) deviate from the expected value (mean).

##### **Definition of Variance**
For a random variable \(X\) with probability distribution \(f(x)\) and mean \(\mu = E(X)\), the variance is given by:
$$
\text{Var}(X) = E[(X - \mu)^2]
$$
Where:
- \(E[(X - \mu)^2]\) represents the expected value of the squared deviations from the mean.

##### **Derivation of Variance Formula**
To derive the variance formula, we start with the definition:
1. Expand \(E[(X - \mu)^2]\):
   $$
   E[(X - \mu)^2] = E[X^2 - 2\mu X + \mu^2]
   $$
2. Use linearity of expectation:
   $$
   E[X^2 - 2\mu X + \mu^2] = E[X^2] - 2\mu E[X] + E[\mu^2]
   $$
3. Recall that \(E[\mu^2] = \mu^2\) (since \(\mu\) is constant) and \(E[X] = \mu\):
   $$
   E[X^2] - 2\mu E[X] + \mu^2 = E[X^2] - 2\mu^2 + \mu^2 = E[X^2] - \mu^2
   $$
Thus:
$$
\text{Var}(X) = E[X^2] - \mu^2
$$

##### **Another Form of the Variance Formula**
In terms of the probability density function \(f(x)\):
- **Discrete Case:**
  $$
  \text{Var}(X) = \sum_{x} (x - \mu)^2 f(x)
  $$
- **Continuous Case:**
  $$
  \text{Var}(X) = \int_{-\infty}^{\infty} (x - \mu)^2 f(x) \, dx
  $$

---

#### **2. Variance of \(g(X)\)**
If \(g(X)\) is a function of a random variable \(X\), the variance of \(g(X)\) is given by:
$$
\text{Var}[g(X)] = E[g(X)^2] - (E[g(X)])^2
$$

##### **Discrete Case:**
For a discrete random variable \(X\) with probability \(P(X = x)\):
$$
\text{Var}[g(X)] = \sum_{x} g(x)^2 P(X = x) - \left(\sum_{x} g(x) P(X = x)\right)^2
$$

##### **Continuous Case:**
For a continuous random variable \(X\) with probability density function \(f(x)\):
$$
\text{Var}[g(X)] = \int_{-\infty}^{\infty} g(x)^2 f(x) \, dx - \left(\int_{-\infty}^{\infty} g(x) f(x) \, dx\right)^2
$$

This captures the spread of transformed data \(g(X)\), extending the variance concept.

---

#### **3. Covariance of \(X\) and \(Y\)**
Covariance measures the relationship or dependency between two random variables \(X\) and \(Y\). It determines how changes in one variable correspond to changes in the other.

##### **Definition of Covariance**
The covariance is defined as:
$$
\text{Cov}(X, Y) = E[(X - \mu_X)(Y - \mu_Y)]
$$
Where:
- \(\mu_X = E(X)\): Mean of \(X\)
- \(\mu_Y = E(Y)\): Mean of \(Y\)

##### **Expanded Formula**
By expanding the product \((X - \mu_X)(Y - \mu_Y)\) and using linearity of expectation:
$$
\text{Cov}(X, Y) = E[XY] - E[X]E[Y]
$$

##### **Properties:**
- \(\text{Cov}(X, X) = \text{Var}(X)\).
- If \(X\) and \(Y\) are independent, \(\text{Cov}(X, Y) = 0\).

---

#### **4. Correlation Coefficient of \(X\) and \(Y\)**
The **correlation coefficient** quantifies the strength and direction of the linear relationship between \(X\) and \(Y\). It is the normalized version of covariance.

##### **Formula**
The correlation coefficient, denoted by \(\rho(X, Y)\) or \(r\), is:
$$
\rho(X, Y) = \frac{\text{Cov}(X, Y)}{\sigma_X \sigma_Y}
$$
Where:
- \(\sigma_X = \sqrt{\text{Var}(X)}\): Standard deviation of \(X\)
- \(\sigma_Y = \sqrt{\text{Var}(Y)}\): Standard deviation of \(Y\)

##### **Range**
The correlation coefficient lies within:
$$
-1 \leq \rho(X, Y) \leq 1
$$
- \(+1\): Perfect positive correlation.
- \(0\): No correlation.
- \(-1\): Perfect negative correlation.

---

This systematic explanation covers the variance, covariance, and correlation concepts, along with relevant derivations and formulas. Let me know if you'd like to explore practical examples or apply these to specific contexts!

### **Means and Variances of Linear Combinations of Random Variables**

Here is a comprehensive explanation of the requested theorems, their equations, and proofs for the given scenarios.

---

#### **Theorem: Expected Value of the Sum or Difference of Two or More Functions**

**Statement:**  
If \( X_1, X_2, ..., X_n \) are random variables and \( a_1, a_2, ..., a_n \) are constants, then the expected value of the linear combination of these random variables is:
$$
E\left( \sum_{i=1}^{n} a_i X_i \right) = \sum_{i=1}^{n} a_i E(X_i)
$$

##### **For the Continuous Case**
Let \( X \) be a continuous random variable with probability density function \( f(x) \). The expected value is defined as:
$$
E(X) = \int_{-\infty}^\infty x f(x) dx
$$

###### **Proof for \( E(aX + b) \):**
1. Start with the definition:
   $$
   E(aX + b) = \int_{-\infty}^\infty (aX + b) f(x) dx
   $$
2. Use linearity of the integral:
   $$
   E(aX + b) = \int_{-\infty}^\infty aX f(x) dx + \int_{-\infty}^\infty b f(x) dx
   $$
3. Factor out constants:
   $$
   E(aX + b) = a \int_{-\infty}^\infty X f(x) dx + b \int_{-\infty}^\infty f(x) dx
   $$
4. Note that \( \int_{-\infty}^\infty f(x) dx = 1 \) (the total probability is 1):
   $$
   E(aX + b) = aE(X) + b
   $$

Thus, the expected value of a linear transformation is:
$$
E(aX + b) = aE(X) + b
$$

---

#### **Theorem: Variance of a Linear Combination**

**Statement:**  
If \( X \) is a random variable with variance \( \text{Var}(X) = \sigma_X^2 \), and \( a, b, \) and \( c \) are constants, then:
1. \( \text{Var}(aX + b) = a^2 \text{Var}(X) \)
2. For a linear combination of independent variables:
$$
\text{Var}\left(\sum_{i=1}^n a_i X_i\right) = \sum_{i=1}^n a_i^2 \text{Var}(X_i)
$$

---

##### **Proof for \( \text{Var}(aX + b) = a^2 \text{Var}(X) \):**
1. Start with the definition of variance:
   $$
   \text{Var}(X) = E\left[(X - \mu)^2\right]
   $$
2. Apply to the linear transformation \( aX + b \):
   $$
   \text{Var}(aX + b) = E\left[(aX + b - E(aX + b))^2\right]
   $$
3. Simplify \( E(aX + b) = aE(X) + b \), so:
   $$
   \text{Var}(aX + b) = E\left[(aX + b - (a\mu + b))^2\right]
   $$
4. Simplify further:
   $$
   \text{Var}(aX + b) = E\left[(aX - a\mu)^2\right]
   $$
5. Factor \( a^2 \) out:
   $$
   \text{Var}(aX + b) = a^2 E\left[(X - \mu)^2\right]
   $$
6. Since \( E\left[(X - \mu)^2\right] = \text{Var}(X) \):
   $$
   \text{Var}(aX + b) = a^2 \text{Var}(X)
   $$

---

#### **Theorem: Covariance of Two Random Variables**

**Statement:**  
If \( X \) and \( Y \) are two random variables, their covariance is defined as:
$$
\text{Cov}(X, Y) = E[(X - E(X))(Y - E(Y))]
$$
This can also be expressed as:
$$
\text{Cov}(X, Y) = E(XY) - E(X)E(Y)
$$

##### **Proof:**
Expand the expectation:
$$
\text{Cov}(X, Y) = E[XY - XE(Y) - YE(X) + E(X)E(Y)]
$$
Using the linearity of expectation:
$$
\text{Cov}(X, Y) = E(XY) - E(X)E(Y) - E(Y)E(X) + E(X)E(Y)
$$
Combine terms:
$$
\text{Cov}(X, Y) = E(XY) - E(X)E(Y)
$$

---

#### **Correlation Coefficient of \( X \) and \( Y \)**

**Statement:**  
The correlation coefficient quantifies the linear relationship between \( X \) and \( Y \):
$$
\rho(X, Y) = \frac{\text{Cov}(X, Y)}{\sigma_X \sigma_Y}
$$
Where:
- \( \sigma_X = \sqrt{\text{Var}(X)} \)
- \( \sigma_Y = \sqrt{\text{Var}(Y)} \)

---

#### **Other Properties**
1. If \( X \) and \( Y \) are independent:
   - \( \text{Cov}(X, Y) = 0 \)
   - \( \text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y) \)
2. Linear combinations of independent variables maintain independence.

Would you like me to expand on specific proofs or provide worked examples for better clarity? Let me know!

