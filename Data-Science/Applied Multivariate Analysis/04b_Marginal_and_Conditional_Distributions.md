# Marginal and Conditional Distribution
## **Marginal Distributions of \( X \) and \( Y \) in Bivariate Normal**

### **Probability Density Function (PDF)**
The joint PDF of the bivariate normal distribution is:
$$
f(x, y) = \frac{1}{2\pi |\Sigma|^{1/2}} \exp\left(-\frac{1}{2} Z(x, y)\right),
$$
where:
1. **Determinant of Covariance Matrix (\(|\Sigma|\)):**
   $$
   |\Sigma| = \sigma_x^2 \sigma_y^2 (1 - \rho^2).
   $$
2. **Quadratic Form (\(Z(x, y)\)):**
   $$
   Z(x, y) = \frac{(x - \mu_x)^2}{\sigma_x^2} - 2\rho \frac{(x - \mu_x)(y - \mu_y)}{\sigma_x \sigma_y} + \frac{(y - \mu_y)^2}{\sigma_y^2}.
   $$

---

### **Finding the Marginal Distribution of \( X \):**

To derive \( f_X(x) \), we integrate \( f(x, y) \) over all possible values of \( y \):
$$
f_X(x) = \int_{-\infty}^\infty f(x, y) \, dy.
$$

#### **Substitute the Bivariate Normal PDF**:
$$
f_X(x) = \int_{-\infty}^\infty \frac{1}{2\pi |\Sigma|^{1/2}} \exp\left(-\frac{1}{2} Z(x, y)\right) \, dy.
$$

#### **Substitute \( Z(x, y) \):**
The quadratic form \( Z(x, y) \) is:
$$
Z(x, y) = \frac{(x - \mu_x)^2}{\sigma_x^2} - 2\rho \frac{(x - \mu_x)(y - \mu_y)}{\sigma_x \sigma_y} + \frac{(y - \mu_y)^2}{\sigma_y^2}.
$$

---

### **Simplify the Exponent:**

1. Combine terms involving \( y \):
   $$
   Z(x, y) = \frac{(x - \mu_x)^2}{\sigma_x^2} + \frac{1}{\sigma_y^2} \left( (y - \mu_y)^2 - 2\rho (y - \mu_y)\frac{\sigma_y}{\sigma_x}(x - \mu_x) \right).
   $$

2. **Complete the Square for \( y \):**
   The term inside the parentheses is:
   $$
   (y - \mu_y)^2 - 2\rho (y - \mu_y)\frac{\sigma_y}{\sigma_x}(x - \mu_x).
   $$
   Completing the square:
   $$
   (y - \mu_y)^2 - 2\rho (y - \mu_y)\frac{\sigma_y}{\sigma_x}(x - \mu_x) = \left( y - \mu_y - \rho \frac{\sigma_y}{\sigma_x}(x - \mu_x) \right)^2 - \left( \rho \frac{\sigma_y}{\sigma_x}(x - \mu_x) \right)^2.
   $$

3. Substitute back into \( Z(x, y) \):
   $$
   Z(x, y) = \frac{(x - \mu_x)^2}{\sigma_x^2} + \frac{\left( y - \mu_y - \rho \frac{\sigma_y}{\sigma_x}(x - \mu_x) \right)^2}{\sigma_y^2} - \frac{\left( \rho \frac{\sigma_y}{\sigma_x}(x - \mu_x) \right)^2}{\sigma_y^2}.
   $$

4. Separate terms involving \( y \):
   $$
   Z(x, y) = \frac{(x - \mu_x)^2 (1 - \rho^2)}{\sigma_x^2} + \frac{\left( y - \mu_y - \rho \frac{\sigma_y}{\sigma_x}(x - \mu_x) \right)^2}{\sigma_y^2}.
   $$

---

### **Perform the Integration:**

Integrating over \( y \) involves the term:
$$
\int_{-\infty}^\infty \exp\left(-\frac{1}{2} \frac{\left( y - \mu_y - \rho \frac{\sigma_y}{\sigma_x}(x - \mu_x) \right)^2}{\sigma_y^2}\right) \, dy.
$$

This is the integral of a normalized Gaussian function with respect to \( y \), which evaluates to 1. Thus, the remaining terms are:
$$
f_X(x) = \frac{1}{\sqrt{2\pi \sigma_x^2}} \exp\left(-\frac{1}{2} \frac{(x - \mu_x)^2}{\sigma_x^2}\right).
$$

---

### **Result:***

The marginal distribution of \( X \) is:
$$
f_X(x) = \frac{1}{\sqrt{2\pi \sigma_x^2}} \exp\left(-\frac{1}{2} \frac{(x - \mu_x)^2}{\sigma_x^2}\right).
$$

This is the **normal PDF** with:
- Mean: \( \mu_x \),
- Variance: \( \sigma_x^2 \).

Similarly, the marginal distribution of \( Y \) is:
$$
f_Y(y) = \frac{1}{\sqrt{2\pi \sigma_y^2}} \exp\left(-\frac{1}{2} \frac{(y - \mu_y)^2}{\sigma_y^2}\right).
$$

---

#### **Conclusion:**
The marginal distributions of \( X \) and \( Y \) in the bivariate normal distribution are themselves normally distributed. This result is obtained by integrating out the other variable and leveraging the properties of Gaussian integrals, which confirm that the integrand is proportional to a un-+ivariate normal density.

## Conditional Distribution

Joint probability density function

$$
f(y_2 | y_1) = \frac{f(y_1, y_2)}{f_1(y_1)} = \frac{1}{2\pi \sqrt{\sigma_1^2 \sigma_2^2 (1 - \rho^2)}} \exp \left\{ - \frac{1}{2(1 - \rho^2)}  \left[ \frac{(y_1 - \mu_1)^2}{\sigma_1^2} - \frac{2\rho (y_1 - \mu_1)(y_2 - \mu_2)}{\sigma_1 \sigma_2} + \frac{(y_2 - \mu_2)^2}{\sigma_2^2} \right]  \right\}
$$

Multiplication factor for marginal PDF

$$ 
\times \frac{1}{\sqrt{2\pi \sigma_1^2}} \exp \left\{ - \frac{(y_1 - \mu_1)^2}{2\sigma_1^2} \right\}
$$

Simplified expression

$$
= \frac{1}{\sqrt{2\pi \sigma_2^2 (1 - \rho^2)}} \exp \left\{ - \frac{1}{2(1 - \rho^2)}  \left[  \frac{(y_1 - \mu_1)^2}{\sigma_1^2}  - \frac{2\rho (y_1 - \mu_1)(y_2 - \mu_2)}{\sigma_1 \sigma_2}  + \frac{(y_2 - \mu_2)^2}{\sigma_2^2}  \right]  + \frac{1}{2} \frac{(y_1 - \mu_1)^2}{\sigma_1^2}  \right\}
$$

Combining terms involving $(y_1 - mu_1)^2$

$$
= \frac{1}{\sqrt{2\pi \sigma_2^2 (1 - \rho^2)}} \exp \left\{ - \frac{1}{2(1 - \rho^2)} \left[ \frac{(y_2 - \mu_2)^2}{\sigma_2^2} - \frac{2\rho (y_1 - \mu_1)(y_2 - \mu_2)}{\sigma_1 \sigma_2} + \frac{(y_1 - \mu_1)^2 \rho^2}{\sigma_1^2} \right] \right\}
$$

\[
= \frac{1}{\sqrt{2\pi\sigma_2^2(1-\rho^2)}}  \exp \left\{  -\frac{1}{2(1-\rho^2)\sigma_2^2}  \left[  (y_2 - \mu_2)^2  - \frac{2\rho\sigma_2(y_1 - \mu_1)(y_2 - \mu_2)}{\sigma_1}  + \frac{(y_1 - \mu_1)^2 \rho^2 \sigma_2^2}{\sigma_1^2}  \right]  \right\}
\]

\[
= \frac{1}{\sqrt{2\pi\sigma_2^2(1-\rho^2)}} 
\exp \left\{ 
-\frac{1}{2(1-\rho^2)\sigma_2^2} 
\left[ 
(y_2 - \mu_2) - \frac{(y_1 - \mu_1)\rho\sigma_2}{\sigma_1} 
\right]^2 
\right\}
\]

\[
= \frac{1}{\sqrt{2\pi\sigma_2^2(1-\rho^2)}} 
\exp \left\{ 
-\frac{1}{2(1-\rho^2)\sigma_2^2} 
\left[ 
y_2 - \left( \mu_2 + \frac{(y_1 - \mu_1)\rho\sigma_2}{\sigma_1} 
\right) 
\right]^2 
\right\}
\]


\[
\Rightarrow \quad Y_2 \mid Y_1 = y_1 \sim \mathcal{N} 
\left[ 
\mu_2 + \frac{(y_1 - \mu_1)\rho\sigma_2}{\sigma_1}, 
\sigma_2^2(1-\rho^2) 
\right]
\]


### **The Equation**

The conditional distribution of a random variable \( Y \) given another random variable \( X \) is normal and is expressed as:
$$
Y \mid x \sim N(\mu_{Y|x}, \sigma^2_{Y|x}),
$$
where the conditional mean (\( \mu_{Y|x} \)) and conditional variance (\( \sigma^2_{Y|x} \)) are given by:
$$
\mu_{Y|x} = \mu_Y + \rho \frac{\sigma_Y}{\sigma_X} (x - \mu_X),
$$
$$
\sigma^2_{Y|x} = \sigma^2_Y (1 - \rho^2).
$$

---

### **The Explanation**

This equation describes the **conditional probability distribution** of a random variable \( Y \), given that the random variable \( X \) takes the value \( x \). The conditional distribution is normal, as denoted by \( N \), with a **mean** \( \mu_{Y|x} \) and a **variance** \( \sigma^2_{Y|x} \). These conditional parameters depend on both the characteristics of \( X \) and \( Y \), as well as their correlation.

1. **Conditional Mean (\( \mu_{Y|x} \)):**
   - The conditional mean represents the expected value of \( Y \) given \( X = x \). It is influenced by:
     - The mean of \( Y \), \( \mu_Y \),
     - The correlation coefficient between \( X \) and \( Y \), \( \rho \),
     - The ratio of the standard deviations of \( Y \) and \( X \) (\( \sigma_Y / \sigma_X \)),
     - The deviation of \( x \) from the mean of \( X \), \( x - \mu_X \).
   - This relationship indicates that the conditional mean is a **linear function of \( x \)**.

2. **Conditional Variance (\( \sigma^2_{Y|x} \)):**
   - The conditional variance quantifies the variability of \( Y \) when \( X = x \). It is proportional to the variance of \( Y \), \( \sigma^2_Y \), but is scaled by \( (1 - \rho^2) \), where \( \rho^2 \) accounts for the extent of linear dependence between \( X \) and \( Y \).
   - The term \( (1 - \rho^2) \) ensures that higher correlation (\( \rho \)) leads to lower conditional variance, reflecting reduced uncertainty about \( Y \) given \( X = x \).

### **Significance**
The equation demonstrates how knowledge of \( X \) affects predictions about \( Y \) in the presence of correlation, a feature central to the **bivariate normal distribution**. The result highlights that \( Y \mid x \) has reduced variance compared to \( Y \) alone, indicating that \( X \) provides useful information about \( Y \). This property is widely applied in fields such as regression analysis and probabilistic modeling.


### Important

For a **bivariate normal distribution**, if the correlation coefficient \( \rho \) between two random variables \( X \) and \( Y \) is zero, then \( X \) and \( Y \) are **independent**.

The bivariate normal distribution is a specific joint probability distribution that describes the behavior of two continuous random variables \( X \) and \( Y \). One of its distinctive properties is the relationship between correlation and independence. 

For two random variables, **correlation** measures the degree and direction of their linear relationship, whereas **independence** implies that knowing the value of one variable provides no information about the other. In most probability distributions, zero correlation does not guarantee independence, as the variables could still be dependent through non-linear relationships.

However, for the bivariate normal distribution, zero correlation (\( \rho = 0 \)) implies **independence**. This is because the joint probability density function (PDF) of a bivariate normal distribution fully characterizes the relationship between \( X \) and \( Y \) as either linear or independent. When \( \rho = 0 \):
1. The joint PDF \( f(x, y) \) simplifies into the product of the marginal PDFs \( f(x) \) and \( f(y) \), i.e.,
   $$
   f(x, y) = f(x)f(y).
   $$
   This factorization confirms independence since the joint probability equals the product of the marginal probabilities.
2. There is no linear dependence or any residual dependence in higher moments, ensuring that the two variables behave independently in every statistical sense.

In summary, this property is unique to the bivariate normal distribution and demonstrates its mathematical elegance and practical utility in modeling dependent continuous variables.


