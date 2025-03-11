# The Likelihood Function

The **likelihood function** is a fundamental concept in statistics, used for parameter estimation within a given statistical model. It helps us determine which parameter value(s) are most likely to have produced the observed data. 

## **What is the Likelihood Function?**
The likelihood function originates from a statistical model, which is a set of possible probability distributions \( \{ f_\theta : \theta \in \Omega \} \). Each distribution \( f_\theta \) in the set is defined by a parameter \( \theta \), which belongs to the parameter space \( \Omega \). 

- The **statistical model** assumes that one of these distributions corresponds to the true, unknown data-generating process.
- The **likelihood function** evaluates how plausible a specific \( \theta \) is, given the observed data.

## **Key Characteristics**
- **For Discrete Data:**  
   The distribution \( f_\theta \) is a **probability mass function (PMF)**. For example:
   $$
   f_\theta(x) = P(X = x \mid \theta)
   $$
   Here, \( f_\theta(x) \) gives the probability of observing \( x \), given the parameter \( \theta \).

- **For Continuous Data:**  
   The distribution \( f_\theta \) is a **probability density function (PDF)**. For example:
   $$
   f_\theta(x) = f(x \mid \theta)
   $$
   Here, \( f_\theta(x) \) represents the relative likelihood of observing \( x \) under \( \theta \).

---

## **Formal Definition**
Let \( X = (X_1, X_2, ..., X_n) \) be a vector of observed data points, assumed to be independently sampled from the distribution \( f_\theta \). The **likelihood function** is defined as:
$$
L(\theta \mid X) = \prod_{i=1}^n f_\theta(X_i)
$$
- \( L(\theta \mid X) \): The likelihood of \( \theta \), given the observed data \( X \).
- \( f_\theta(X_i) \): The probability (or density) of observing \( X_i \) under \( \theta \).

If \( \theta = (\mu, \sigma^2) \), where \( \mu \) is the mean and \( \sigma^2 \) is the variance (or standard deviation squared), the likelihood function and related equations can be derived as follows:

### **Log-Likelihood Function**
In practice, it is often easier to work with the **log-likelihood function**, which is the natural logarithm of the likelihood:
$$
\ell(\theta \mid X) = \ln L(\theta \mid X) = \sum_{i=1}^n \ln f_\theta(X_i)
$$
- Log-likelihood simplifies computations, particularly when maximizing the likelihood to find the best parameter estimates.

---

## **Independent and Identically Distributed (I.I.D) Random Variables**
Let \( X_1, X_2, ..., X_n \) be independent and identically distributed (i.i.d.) random variables following a normal distribution \( N(\mu, \sigma^2) \). The probability density function (PDF) for each \( X_i \) is:
$$
f(x_i \mid \mu, \sigma^2) = \frac{1}{\sqrt{2\pi \sigma^2}} e^{-\frac{(x_i - \mu)^2}{2\sigma^2}}
$$

The likelihood function for the parameter set \( \theta = (\mu, \sigma^2) \), given the observed data \( X = (X_1, X_2, ..., X_n) \), is:
$$
L(\mu, \sigma^2 \mid X) = \prod_{i=1}^n f(x_i \mid \mu, \sigma^2)
$$

Substituting the PDF into the likelihood function:
$$
L(\mu, \sigma^2 \mid X) = \prod_{i=1}^n \frac{1}{\sqrt{2\pi \sigma^2}} e^{-\frac{(x_i - \mu)^2}{2\sigma^2}}
$$
$$
L(\mu, \sigma^2 \mid X) = \left(\frac{1}{\sqrt{2\pi \sigma^2}}\right)^n e^{-\frac{1}{2\sigma^2} \sum_{i=1}^n (x_i - \mu)^2}
$$

---

### **Log-Likelihood Function**
Taking the natural logarithm of the likelihood function simplifies computation:
$$
\ell(\mu, \sigma^2 \mid X) = \ln L(\mu, \sigma^2 \mid X)
$$
$$
\ell(\mu, \sigma^2 \mid X) = n \ln \left( \frac{1}{\sqrt{2\pi \sigma^2}} \right) - \frac{1}{2\sigma^2} \sum_{i=1}^n (x_i - \mu)^2
$$
$$
\ell(\mu, \sigma^2 \mid X) = -\frac{n}{2} \ln(2\pi) - \frac{n}{2} \ln(\sigma^2) - \frac{1}{2\sigma^2} \sum_{i=1}^n (x_i - \mu)^2
$$

---

### **Maximum Likelihood Estimation (MLE)**
To estimate the parameters \( \mu \) and \( \sigma^2 \) using MLE:
1. Differentiate the log-likelihood function with respect to \( \mu \) and \( \sigma^2 \).
2. Set the derivatives to zero and solve for the parameters.

#### **MLE for \( \mu \):**
Differentiate with respect to \( \mu \):
$$
\frac{\partial \ell}{\partial \mu} = \frac{1}{\sigma^2} \sum_{i=1}^n (x_i - \mu)
$$
Set \( \frac{\partial \ell}{\partial \mu} = 0 \):
$$
\sum_{i=1}^n (x_i - \mu) = 0
$$
$$
\mu = \frac{1}{n} \sum_{i=1}^n x_i
$$
Thus, the MLE for \( \mu \) is the sample mean.

#### **MLE for \( \sigma^2 \):**
Differentiate with respect to \( \sigma^2 \):
$$
\frac{\partial \ell}{\partial \sigma^2} = -\frac{n}{2\sigma^2} + \frac{1}{2\sigma^4} \sum_{i=1}^n (x_i - \mu)^2
$$
Set \( \frac{\partial \ell}{\partial \sigma^2} = 0 \):
$$
-\frac{n}{2\sigma^2} + \frac{1}{2\sigma^4} \sum_{i=1}^n (x_i - \mu)^2 = 0
$$
Multiply through by \( 2\sigma^4 \):
$$
-n\sigma^2 + \sum_{i=1}^n (x_i - \mu)^2 = 0
$$
$$
\sigma^2 = \frac{1}{n} \sum_{i=1}^n (x_i - \mu)^2
$$
Thus, the MLE for \( \sigma^2 \) is the sample variance.

---

## **Key Differences Between Likelihood and Probability**
1. **Probability:**
   - Represents the likelihood of future observations, assuming known parameters \( \theta \).
   - Example: \( P(X = x \mid \theta) \).

2. **Likelihood:**
   - Evaluates how likely specific parameter values \( \theta \) are, given observed data \( X \).
   - Example: \( L(\theta \mid X) \).

---

#### **Applications of the Likelihood Function**
1. **Maximum Likelihood Estimation (MLE):**
   - Finds the parameter \( \theta \) that maximizes the likelihood function:
     $$
     \hat{\theta}_{\text{MLE}} = \underset{\theta}{\text{argmax}} \, L(\theta \mid X)
     $$
   - This provides the parameter estimate most likely to have generated the observed data.

2. **Model Comparison:**
   - Likelihood functions can be used to compare statistical models, often through metrics like the **Akaike Information Criterion (AIC)** or the **Bayesian Information Criterion (BIC)**.

3. **Bayesian Inference:**
   - In Bayesian statistics, the likelihood is combined with a prior distribution to update beliefs about \( \theta \) using observed data via Bayes' theorem:
     $$
     P(\theta \mid X) \propto L(\theta \mid X) \cdot P(\theta)
     $$

---

## Mean Estimator

### **Definition**
A **mean estimator** is a statistical measure used to estimate the central tendency or average of a population or sample. It plays a crucial role in statistical inference and data analysis.

---

### **Formula**
For a set of \( n \) data points \( X = \{x_1, x_2, ..., x_n\} \), the mean (also called the sample mean) is defined as:
$$
\hat{\mu} = \bar{X} = \frac{1}{n} \sum_{i=1}^n x_i
$$
Where:
- \( \hat{\mu} \): Estimate of the population mean.
- \( x_i \): Observed values.
- \( n \): Total number of observations.

---

### **Key Properties**
1. **Unbiasedness**:
   - The sample mean is an unbiased estimator of the population mean:
     $$
     E[\bar{X}] = \mu
     $$
   - This means that, on average, the sample mean equals the true population mean.

2. **Efficiency**:
   - Among all linear unbiased estimators, the sample mean has the smallest variance.

3. **Consistency**:
   - As the sample size \( n \) increases, the sample mean converges to the population mean:
     $$
     \lim_{n \to \infty} \bar{X} = \mu
     $$

4. **Normality (Central Limit Theorem)**:
   - For large \( n \), the sampling distribution of \( \bar{X} \) approaches a normal distribution:
     $$
     \bar{X} \sim N\left(\mu, \frac{\sigma^2}{n}\right)
     $$
   - Where \( \sigma^2 \) is the population variance.

---

### **Examples**
1. **Sample Mean**:
   For \( X = \{3, 7, 8, 10, 15\} \), the mean is:
   $$
   \bar{X} = \frac{1}{5} (3 + 7 + 8 + 10 + 15) = 8.6
   $$

2. **Population Mean Estimation**:
   In a survey of heights, if the sample mean height is 170 cm, this is an estimate of the population mean height.

---

### **Applications**
- **Statistical Inference**: Used to draw conclusions about the population.
- **Regression Analysis**: Helps in determining trends and predictions.
- **Hypothesis Testing**: Used as a test statistic in \( t \)-tests and other tests.
- **Data Summarization**: Provides a concise summary of the central tendency of data.

---

## Variance Estimator

### **Definition**
A **variance estimator** is a statistical measure used to quantify the spread or variability of a random variable. It estimates how much the values in a dataset deviate from their mean.

---

### **Formula**
For a dataset \( X = \{x_1, x_2, ..., x_n\} \), the variance is estimated using the following formula:

#### **Sample Variance (Unbiased Estimator):**
$$
\hat{\sigma}^2 = \frac{1}{n-1} \sum_{i=1}^n (x_i - \bar{X})^2
$$
Where:
- \( \hat{\sigma}^2 \): Sample variance (estimate of the population variance).
- \( x_i \): Individual data points.
- \( \bar{X} = \frac{1}{n} \sum_{i=1}^n x_i \): Sample mean.
- \( n \): Total number of observations.

#### **Population Variance:**
If all data points from the population are known, the variance is given by:
$$
\sigma^2 = \frac{1}{n} \sum_{i=1}^n (x_i - \mu)^2
$$
Where \( \mu \) is the true population mean.

---

### **Key Properties**
1. **Unbiasedness**:
   - The sample variance \( \hat{\sigma}^2 \) is an unbiased estimator of the population variance:
     $$
     E[\hat{\sigma}^2] = \sigma^2
     $$

2. **Consistency**:
   - As the sample size \( n \) increases, \( \hat{\sigma}^2 \) converges to the population variance \( \sigma^2 \):
     $$
     \lim_{n \to \infty} \hat{\sigma}^2 = \sigma^2
     $$

3. **Efficiency**:
   - \( \hat{\sigma}^2 \) minimizes mean squared error among unbiased estimators.

4. **Centrality**:
   - Variance measures how data points cluster around the mean.

---

### **Examples**
1. **Sample Variance Calculation**:
   For \( X = \{3, 7, 8, 10, 15\} \):
   - Compute the mean:
     $$
     \bar{X} = \frac{1}{5} (3 + 7 + 8 + 10 + 15) = 8.6
     $$
   - Compute the variance:
     $$
     \hat{\sigma}^2 = \frac{1}{5-1} \left[ (3-8.6)^2 + (7-8.6)^2 + (8-8.6)^2 + (10-8.6)^2 + (15-8.6)^2 \right]
     $$
     $$
     \hat{\sigma}^2 = \frac{1}{4} (31.36 + 2.56 + 0.36 + 1.96 + 40.96) = \frac{77.2}{4} = 19.3
     $$

2. **Population Variance**:
   If all data from the population is known, use the formula for \( \sigma^2 \) without subtracting 1 from \( n \).

---

### **Applications**
- **Risk Analysis**: Variance is used in finance to measure the risk of investments.
- **Data Variability**: Provides insights into the spread of data in fields like quality control and experimentation.
- **Statistical Inference**: Variance estimation is essential for hypothesis testing and constructing confidence intervals.

---

## **Distribution Estimator: Shape**

### **Definition**
The **shape** of a distribution refers to the graphical representation or pattern of how data points are distributed across values. Estimating the shape of a distribution helps in understanding its central tendency, variability, skewness, and kurtosis.

---

### **Key Characteristics of Shape**

1. **Symmetry:**
   - A distribution is **symmetric** if the left and right sides of its graph are mirror images.
   - **Example:** The normal distribution is symmetric.

2. **Skewness:**
   - Measures the asymmetry of the distribution.
     - **Positive skew:** The tail is longer on the right (e.g., income data).
     - **Negative skew:** The tail is longer on the left.

3. **Modality:**
   - Refers to the number of peaks (modes) in the distribution.
     - **Unimodal:** One peak (e.g., height distribution).
     - **Bimodal:** Two peaks (e.g., test scores with two groups).
     - **Multimodal:** More than two peaks.

4. **Tailedness (Kurtosis):**
   - Measures the thickness of the tails relative to a normal distribution.
     - **Leptokurtic:** Heavy tails, sharp peak.
     - **Mesokurtic:** Normal tails (e.g., normal distribution).
     - **Platykurtic:** Light tails, flat peak.

---

### **Methods to Estimate Shape**

#### **1. Graphical Visualization**
   - **Histograms:**
     - Provides a visual summary of data distribution by grouping values into bins.
   - **Boxplots:**
     - Helps visualize skewness and spread.
   - **Density Plots:**
     - Smooth curve to represent the probability density function.

#### **2. Numerical Summaries**
   - **Skewness Coefficient:**
     $$
     \text{Skewness} = \frac{E[(X - \mu)^3]}{\sigma^3}
     $$
     - Positive skewness indicates a long right tail.
     - Negative skewness indicates a long left tail.

   - **Kurtosis Coefficient:**
     $$
     \text{Kurtosis} = \frac{E[(X - \mu)^4]}{\sigma^4}
     $$
     - Higher kurtosis indicates heavier tails.

---

### **Applications**
1. **Data Analysis:**
   - Understanding the shape of a distribution aids in selecting appropriate statistical methods (e.g., normality assumptions for hypothesis testing).
2. **Predictive Modeling:**
   - Shape estimation helps identify patterns, anomalies, and trends.
3. **Risk Assessment:**
   - Heavy-tailed distributions may indicate extreme risks in financial and insurance data.

---

## Interval Estimator

## **Definition**
An **interval estimator** provides a range of values, called a confidence interval, within which the true value of a population parameter is likely to fall. Unlike point estimators, which give a single value, interval estimators incorporate uncertainty, offering more robust conclusions about the parameter.

---

### **Components of an Interval Estimator**
1. **Point Estimate**:
   - The center of the interval, typically the value obtained from a sample (e.g., sample mean \( \bar{X} \)).
2. **Margin of Error**:
   - Accounts for the uncertainty in the estimate and is determined by the standard error and the critical value from a statistical distribution.
   - Formula:
     $$
     \text{Margin of Error} = z^* \cdot \text{SE}
     $$
     Where:
     - \( z^* \): Critical value from the standard normal or \( t \)-distribution.
     - \( \text{SE} \): Standard error of the estimator.

---

### **Formula for a Confidence Interval**
For a population parameter \( \theta \), the confidence interval is given by:
$$
\text{CI} = \text{Point Estimate} \pm \text{Margin of Error}
$$

#### **Common Scenarios:**
1. **Confidence Interval for the Mean (\( \mu \)):**
   - When the population standard deviation \( \sigma \) is known:
     $$
     \text{CI} = \bar{X} \pm z^* \cdot \frac{\sigma}{\sqrt{n}}
     $$
   - When \( \sigma \) is unknown, use the \( t \)-distribution:
     $$
     \text{CI} = \bar{X} \pm t^* \cdot \frac{s}{\sqrt{n}}
     $$
     Where:
     - \( s \): Sample standard deviation.

2. **Confidence Interval for a Proportion (\( p \)):**
   $$
   \text{CI} = \hat{p} \pm z^* \cdot \sqrt{\frac{\hat{p}(1 - \hat{p})}{n}}
   $$
   Where:
   - \( \hat{p} \): Sample proportion.
   - \( n \): Sample size.

---

### **Key Terms**
1. **Confidence Level**:
   - Indicates the percentage of confidence intervals that will contain the true parameter value if repeated sampling is conducted.
   - Common levels: 90%, 95%, 99%.

2. **Critical Value (\( z^* \) or \( t^* \))**:
   - Represents the number of standard deviations required to reach a specified confidence level.

3. **Standard Error (SE)**:
   - Measures the variability of the sampling distribution.

---

### **Examples**
1. **Confidence Interval for Mean**:
   - Sample data: \( \bar{X} = 100 \), \( \sigma = 15 \), \( n = 25 \), \( z^* = 1.96 \) (for 95% confidence).
   - Margin of Error:
     $$
     \text{ME} = 1.96 \cdot \frac{15}{\sqrt{25}} = 5.88
     $$
   - Confidence Interval:
     $$
     \text{CI} = 100 \pm 5.88 = (94.12, 105.88)
     $$

2. **Confidence Interval for Proportion**:
   - Sample data: \( \hat{p} = 0.6 \), \( n = 100 \), \( z^* = 1.96 \).
   - Margin of Error:
     $$
     \text{ME} = 1.96 \cdot \sqrt{\frac{0.6(1 - 0.6)}{100}} = 0.096
     $$
   - Confidence Interval:
     $$
     \text{CI} = 0.6 \pm 0.096 = (0.504, 0.696)
     $$

---

### **Applications**
1. **Hypothesis Testing**:
   - Confidence intervals can be used to test claims about population parameters.
2. **Decision-Making**:
   - Interval estimates are widely used in quality control, finance, healthcare, and survey results to support decisions under uncertainty.
3. **Risk Analysis**:
   - Confidence intervals provide ranges for assessing risks and planning contingencies.

