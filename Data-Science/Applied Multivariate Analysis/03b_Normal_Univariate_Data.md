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
The covariance of \(X\) and \(Y\) is defined as:
$$
\text{Cov}(X, Y) = E[(X - \mu_X)(Y - \mu_Y)]
$$
Where:
- \(\mu_X = E(X)\): Mean of \(X\)
- \(\mu_Y = E(Y)\): Mean of \(Y\)
###### **Calculation**
$$
\sigma_{XY} = \text{Cov}(X, Y) $$
$$ = E[(X - \mu_X)(Y - \mu_Y)] $$
Discrete
$$ = \sum_{x} \sum_{y} (x - \mu_X)(y - \mu_Y) f(x, y) $$
Continuous
$$ = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} (x - \mu_X)(y - \mu_Y) f(x, y) \, dx \, dy 
$$

###### **Common Form**
By expanding the product \((X - \mu_X)(Y - \mu_Y)\) and using linearity of expectation:
$$
\text{Cov}(X, Y) = E[XY] - E[X]E[Y]
$$

###### **Properties:**
- \(\text{Cov}(X, X) = \text{Var}(X)\).
- If \(X\) and \(Y\) are independent, \(\text{Cov}(X, Y) = 0\).

---

#### **4. Correlation Coefficient of \(X\) and \(Y\)**
The **correlation coefficient** quantifies the strength and direction of the linear relationship between \(X\) and \(Y\). It is the normalized version of covariance.

##### **Formula**
The correlation coefficient, denoted by \(\rho(X, Y)\) or \(r\), is:
$$
\rho(X, Y) = \frac{\text{Cov}(X, Y)}{\sigma_X \sigma_Y} = \frac{\text{Cov}(X, Y)}{\sqrt{\text{Var}(X)}\sqrt{\text{Var}(Y)}}
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

#### **Linear Combinations of Random Variables**

##### **Theorem: Expected Value of the Sum or Difference of Two or More Functions**

**Statement:**  
The expected value of the sum or difference of two or more functions of random variables \( X \) and \( Y \) is the sum or difference of the expected values of those functions. This can be expressed as:
$$
E[g(X, Y) \pm h(X, Y)] = E[g(X, Y)] \pm E[h(X, Y)].
$$

---

###### **For the Continuous Case**
Let \( X \) and \( Y \) be continuous random variables with a joint probability density function \( f(x, y) \). The expected value of their sum or difference is given as:
$$
E[g(X, Y) \pm h(X, Y)] = \iint [g(x, y) \pm h(x, y)] f(x, y) \, dx \, dy.
$$

###### **Step-by-Step Proof**  
1. Start with the definition of expected value for the continuous case:
   $$
   E[g(X, Y) \pm h(X, Y)] = \iint [g(x, y) \pm h(x, y)] f(x, y) \, dx \, dy.
   $$
2. Apply the linearity property of integrals:
   $$
   E[g(X, Y) \pm h(X, Y)] = \iint g(x, y) f(x, y) \, dx \, dy \pm \iint h(x, y) f(x, y) \, dx \, dy.
   $$
3. By the definition of expected value:
   $$
   E[g(X, Y) \pm h(X, Y)] = E[g(X, Y)] \pm E[h(X, Y)].
   $$

---

##### **Theorem: If \(a\), \(b\), and \(c\) are constants, then**

$$E(aX+bY+c)=aE(X)+bE(Y)+c$$
and
$$\text{Var}(aX+bY+c)=a^2\text{Var}(X)+b^2\text{Var}(Y)+2ab\text{Cov}(X,Y)$$

###### Proof

1. **Linearity of Expectation**:
   The expectation operator \(E\) is linear, meaning:
   $$E(aX + bY + c) = E(aX) + E(bY) + E(c)$$

2. **Constants and Expectation**:
   For any constant \(k\), \(E(k) = k\). Therefore:
   $$E(c) = c$$

3. **Scaling Property**:
   For any random variable \(Z\) and constant \(k\), \(E(kZ) = kE(Z)\). Therefore:
   $$E(aX) = aE(X) \quad \text{and} \quad E(bY) = bE(Y)$$

Combining these results, we get:
$$E(aX + bY + c) = aE(X) + bE(Y) + c$$

1. **Variance Definition**:
   The variance of a random variable \(Z\) is defined as:
   $$\text{Var}(Z) = E[(Z - E(Z))^2]$$

2. **Variance of a Linear Combination**:
   For \(Z = aX + bY + c\), we have:
   $$\text{Var}(aX + bY + c) = E[(aX + bY + c - E(aX + bY + c))^2]$$

3. **Expectation of the Linear Combination**:
   From the first proof, we know:
   $$E(aX + bY + c) = aE(X) + bE(Y) + c$$

4. **Subtracting the Expectation**:
   Therefore:
   $$aX + bY + c - E(aX + bY + c) = aX + bY + c - (aE(X) + bE(Y) + c) = a(X - E(X)) + b(Y - E(Y))$$

5. **Variance Calculation**:
   Now, we calculate the variance:
   $$\text{Var}(aX + bY + c) = E[(a(X - E(X)) + b(Y - E(Y)))^2]$$

6. **Expanding the Square**:
   Expanding the square inside the expectation:
   $$E[(a(X - E(X)) + b(Y - E(Y)))^2] = E[a^2(X - E(X))^2 + b^2(Y - E(Y))^2 + 2ab(X - E(X))(Y - E(Y))]$$

7. **Linearity of Expectation**:
   Using the linearity of expectation:
   $$E[a^2(X - E(X))^2 + b^2(Y - E(Y))^2 + 2ab(X - E(X))(Y - E(Y))] = a^2E[(X - E(X))^2] + b^2E[(Y - E(Y))^2] + 2abE[(X - E(X))(Y - E(Y))]$$

8. **Variance and Covariance**:
   By definition, \(\text{Var}(X) = E[(X - E(X))^2]\) and \(\text{Cov}(X, Y) = E[(X - E(X))(Y - E(Y))]\). Therefore:
   $$\text{Var}(aX + bY + c) = a^2\text{Var}(X) + b^2\text{Var}(Y) + 2ab\text{Cov}(X, Y)$$

###### Corolary
$$ 
\begin{aligned}
    \mathbb{E}(c) &= c & \quad \text{Var}(c) &= 0 \\
    \mathbb{E}(X + c) &= \mathbb{E}(X) + c & \quad \text{Var}(X + c) &= \text{Var}(X) \\
    \mathbb{E}(aX) &= a\mathbb{E}(X) & \quad \text{Var}(aX) &= a^2 \text{Var}(X) \\
    \mathbb{E}(aX + c) &= a\mathbb{E}(X) + c & \quad \text{Var}(aX + c) &= a^2 \text{Var}(X)
\end{aligned}
$$

##### **Theorem: Let \(X\) and \(Y\) be two independent random variables. Then**
$$ E(XY) = E(X)E(Y) $$

###### **Proof for Continuous case,**
$$
\begin{aligned}
    \mathbb{E}(XY) &= \int \int xy f(x,y) \ dx dy \\
                   &= \int \int xy g(x) h(y) \ dx dy \\
                   &= \left[ \int x g(x) \ dx \right] \left[ \int y h(y) \ dy \right] \\
                   &= \mathbb{E}(X) \mathbb{E}(Y)
\end{aligned}
$$

###### Corollary
$$
\textbf{\textcolor{blue}{Corollary.}}\quad Let\ \ X \ \text{and}\ \ Y \ \text{be two independent random variables.} \\
\text{Then} \\ $$
\[\sigma_{XY} = \text{Cov}(X,Y) = 0.\]
$$
\textbf{\textcolor{blue}{Corollary.}}\quad If\ \ X \ \text{and}\ \ Y \ \text{are independent random variables, then} \\$$
\[\text{Var}(aX \pm bY) = a^2 \text{Var}(X) + b^2 \text{Var}(Y).\]
$$
\textbf{\textcolor{blue}{Corollary.}}\quad If\ \ X_1, X_2, \dots, X_n \ \text{are independent random variables, then} \\ $$
\[\text{Var} \left( \sum_{i=1}^{n} a_i X_i \right) = \sum_{i=1}^{n} a_i^2 \text{Var}(X_i).\]

**Other properties**
$$
\begin{aligned}
E \left( \sum_{i=1}^{n} a_i X_i \right) &= \sum_{i=1}^{n} a_i E(X_i) \\
\text{Var} \left( \sum_{i=1}^{n} a_i X_i \right) &= \sum_{i=1}^{n} \sum_{j=1}^{n} a_i a_j \text{Cov}(X_i, X_j) \\
&= \sum_{i=1}^{n} a_i^2 \text{Var}(X_i) + \sum_{i \neq j} a_i a_j \text{Cov}(X_i, X_j) \\
&= \sum_{i=1}^{n} a_i^2 \text{Var}(X_i) + 2 \sum_{1 \leq i < j \leq n} a_i a_j \text{Cov}(X_i, X_j) \\
\text{Cov} \left( \sum_{i=1}^{n} a_i X_i, \sum_{j=1}^{m} b_j Y_j \right) &= \sum_{i=1}^{n} \sum_{j=1}^{m} a_i b_j \text{Cov}(X_i, Y_j)
\end{aligned}
$$

and another properties

$$
\begin{align*}
\text{Cov}(X, a) &= 0 \\
\text{Cov}(X, X) &= \text{Var}(X) \\
\text{Cov}(X, Y) &= \text{Cov}(Y, X) \\
\text{Cov}(aX, bY) &= ab \, \text{Cov}(X, Y) \\
\text{Cov}(X + a, Y + b) &= \text{Cov}(X, Y) \\
\text{Cov}(aX + bY, cZ + dW) &= ac \, \text{Cov}(X, Z) + ad \, \text{Cov}(X, W) \\
&\quad + bc \, \text{Cov}(Y, Z) + bd \, \text{Cov}(Y, W)
\end{align*}
$$
