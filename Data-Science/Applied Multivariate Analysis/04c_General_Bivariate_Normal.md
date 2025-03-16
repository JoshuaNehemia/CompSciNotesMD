# General Bivariate Normal Distribution

## Introduction

The **bivariate normal distribution** is a fundamental concept in statistics that extends the univariate normal distribution to two dimensions. This distribution is particularly useful in multivariate analysis, where relationships between two normally distributed variables are studied. In this discussion, we will explore the definition, properties, and derivation of the **general bivariate normal distribution**, ensuring clarity in each step.

## Constructing the Bivariate Normal Distribution

To construct a bivariate normal distribution, we start with two independent standard normal variables:

\[ Z_1, Z_2 \sim \mathcal{N}(0,1) \]

The probability density function (PDF) of these variables is given by:

\[ f(z_1, z_2) = \frac{1}{2\pi} \exp \left( -\frac{1}{2} (z_1^2 + z_2^2) \right) \]

We now introduce transformations to obtain two correlated normal variables with arbitrary means and variances:

\[ X = \sigma_X Z_1 + \mu_X \]
\[ Y = \sigma_Y [\rho Z_1 + \sqrt{1 - \rho^2}Z_2] + \mu_Y \]

Here, \( \sigma_X \) and \( \sigma_Y \) are the standard deviations of \( X \) and \( Y \), while \( \mu_X \) and \( \mu_Y \) represent their means. The parameter \( \rho \) controls the correlation between \( X \) and \( Y \), ensuring that they are not independent.

## Marginal Distributions of \( X \) and \( Y \)

To analyze the properties of the transformed variables, we determine their individual (marginal) distributions. Since \( Z_1 \sim \mathcal{N}(0,1) \), applying the transformation:

\[ X = \sigma_X Z_1 + \mu_X \]

yields:

\[ X \sim \mathcal{N}(\mu_X, \sigma_X^2) \]

Similarly, expanding the transformation for \( Y \):

\[ Y = \sigma_Y [\rho Z_1 + \sqrt{1 - \rho^2}Z_2] + \mu_Y \]

Since \( Z_1 \) and \( Z_2 \) are standard normal and independent, their linear combination remains normally distributed, leading to:

\[ Y \sim \mathcal{N}(\mu_Y, \sigma_Y^2) \]

Thus, both \( X \) and \( Y \) individually follow normal distributions with their specified means and variances.

## Covariance and Correlation of \( X \) and \( Y \)

The relationship between \( X \) and \( Y \) is captured by their covariance:

\[ \text{Cov}(X, Y) = E[(X - E(X))(Y - E(Y))] \]

Substituting the expressions for \( X \) and \( Y \):

\[ E \left[ (\sigma_X Z_1)(\sigma_Y [\rho Z_1 + \sqrt{1 - \rho^2}Z_2]) \right] \]

Expanding the expectation:

\[ \sigma_X \sigma_Y E \left[ Z_1 \rho Z_1 + Z_1 \sqrt{1 - \rho^2}Z_2 \right] \]

Since \( E[Z_1^2] = 1 \) and \( E[Z_1 Z_2] = 0 \) (as \( Z_1 \) and \( Z_2 \) are independent), we obtain:

\[ \text{Cov}(X, Y) = \sigma_X \sigma_Y \rho \]

Thus, the correlation coefficient \( \rho(X, Y) \) is:

\[ \rho(X,Y) = \frac{\text{Cov}(X, Y)}{\sigma_X \sigma_Y} = \rho \]

This confirms that \( \rho \) is indeed the correlation coefficient between \( X \) and \( Y \).

## Bivariate Normal Random Variables

To generate random variables following a **bivariate normal distribution** with given means, variances, and correlation, we apply the transformations:

\[ X = \sigma_X Z_1 + \mu_X \]
\[ Y = \sigma_Y [\rho Z_1 + \sqrt{1 - \rho^2}Z_2] + \mu_Y \]

This method is particularly useful in simulations, allowing us to sample from a bivariate normal distribution using independent standard normal variables.

The **general bivariate normal distribution** extends the normal distribution to two dimensions, allowing for the modeling of correlated variables. Through linear transformations of standard normal variables, we derive the desired means, variances, and correlation. The derivation of marginal distributions, covariance, and correlation ensures a deep understanding of this important statistical concept, which finds applications in fields ranging from finance to machine learning.

Understanding this distribution is crucial for statistical modeling, as it serves as the foundation for more complex **multivariate normal distributions** used in high-dimensional data analysis.

I will now provide a well-structured academic explanation of the content in the image. Here’s how I will format it:

1. **Statement from the Slide** – The exact text or formula.
2. **Explanation** – A thorough academic explanation covering the meaning, reasoning, and implications of the statement.

---

### **Transformation of Joint Distributions**
*"Let \(X_1, \dots, X_n\) have a continuous joint distribution with probability density function (pdf) \( f \) defined on \( S \). We can define \( n \) new random variables \( Y_1, \dots, Y_n \) as follows:"*
\[
Y_1 = r_1(X_1, \dots, X_n), \quad \dots, \quad Y_n = r_n(X_1, \dots, X_n)
\]

This statement describes the transformation of a set of \( n \) jointly distributed random variables \( X_1, \dots, X_n \) into another set of \( n \) new variables \( Y_1, \dots, Y_n \). The functions \( r_1, \dots, r_n \) define this transformation, mapping the original space \( S \) into a new space \( T \). This transformation is critical in probability and statistics, particularly when changing the variable representation of a distribution.

*"If we assume that the \( n \) functions \( r_1, \dots, r_n \) define a one-to-one differentiable transformation from \( S \) to \( T \), then let the inverse of this transformation be:"*
\[
x_1 = s_1(y_1, \dots, y_n), \quad \dots, \quad x_n = s_n(y_1, \dots, y_n)
\]

For a transformation to be valid in a probability density context, it must be one-to-one and differentiable. This ensures that each set of values in the original space uniquely corresponds to a set of values in the transformed space. The existence of an inverse function \( s_1, \dots, s_n \) ensures that we can recover the original variables \( X_1, \dots, X_n \) from the transformed variables \( Y_1, \dots, Y_n \). This is a crucial requirement for performing probability transformations and ensuring that the probability distribution is well-defined.

*"Then the joint pdf \( g \) of \( Y_1, \dots, Y_n \) is:"*
\[
g(y_1, \dots, y_n) =
\begin{cases} 
f(s_1, \dots, s_n) |J|, & \text{for } (y_1, \dots, y_n) \in T \\
0, & \text{otherwise}
\end{cases}
\]

This formula expresses the probability density function (pdf) of the transformed random variables \( Y_1, \dots, Y_n \) in terms of the original pdf \( f(X_1, \dots, X_n) \). The absolute value of the determinant of the Jacobian matrix \( J \) accounts for the change in volume when transforming coordinates. The transformation ensures that the probability distribution remains consistent between the original and transformed variables. If the transformed variables lie outside the domain \( T \), their probability density is zero.

*"Where the Jacobian determinant is given by:"*
\[
J = \det
\begin{bmatrix}
\frac{\partial s_1}{\partial y_1} & \dots & \frac{\partial s_1}{\partial y_n} \\
\vdots & \ddots & \vdots \\
\frac{\partial s_n}{\partial y_1} & \dots & \frac{\partial s_n}{\partial y_n}
\end{bmatrix}
\]

The Jacobian determinant represents the scaling factor of the transformation when changing variables in a multivariate distribution. It measures how the volume element transforms under the function mapping. A large determinant indicates a stretching transformation, while a small determinant indicates contraction. The absolute value is taken to ensure that probability densities remain non-negative. This concept is essential in multivariate probability and statistical transformations, such as the derivation of distributions under nonlinear transformations.

This framework provides a rigorous approach to transforming multivariate probability distributions. By ensuring the transformation is one-to-one and differentiable, and by incorporating the Jacobian determinant, we can properly derive the new probability density function in the transformed space. This technique is widely used in statistics, econometrics, and machine learning for variable transformations and inference.

### 1. Transformations of Joint Distributions
Consider a set of continuous random variables \(X_1, X_2, \dots, X_n\) with a joint probability density function (pdf) \(f\), defined over a domain \(S\). We introduce a transformation where new random variables \(Y_1, Y_2, \dots, Y_n\) are defined as functions of \(X_1, X_2, \dots, X_n\):
\[
Y_1 = r_1(X_1, \dots, X_n), \quad \dots, \quad Y_n = r_n(X_1, \dots, X_n)
\]

If the functions \(r_1, \dots, r_n\) define a one-to-one, differentiable transformation from \(S\) to \(T\), the inverse transformation is given by:
\[
X_1 = s_1(Y_1, \dots, Y_n), \quad \dots, \quad X_n = s_n(Y_1, \dots, Y_n)
\]

The joint pdf \(g\) of \(Y_1, \dots, Y_n\) is determined by:
\[
g(y_1, \dots, y_n) = \begin{cases} f(s_1, \dots, s_n) |J| & \text{for } (y_1, \dots, y_n) \in T \\ 0 & \text{otherwise} \end{cases}
\]
where \(J\) is the determinant of the Jacobian matrix:
\[
J = \det \begin{bmatrix} \frac{\partial s_1}{\partial y_1} & \cdots & \frac{\partial s_1}{\partial y_n} \\ \vdots & \ddots & \vdots \\ \frac{\partial s_n}{\partial y_1} & \cdots & \frac{\partial s_n}{\partial y_n} \end{bmatrix}
\]

### 2. Bivariate Normal Transformation
To transform the standard normal variables \(Z_1, Z_2\) into correlated variables \(X, Y\), we use the following transformation:
\[
X = \sigma_X Z_1 + \mu_X, \quad Z_1 = \frac{X - \mu_X}{\sigma_X}
\]
\[
Y = \sigma_Y[\rho Z_1 + \sqrt{1 - \rho^2} Z_2] + \mu_Y
\]
Solving for \(Z_2\), we obtain:
\[
Z_2 = \frac{1}{\sqrt{1 - \rho^2}} \left[ \frac{Y - \mu_Y}{\sigma_Y} - \rho \frac{X - \mu_X}{\sigma_X} \right]
\]
Thus, the inverse transformation functions are:
\[
s_1(x,y) = \frac{x - \mu_X}{\sigma_X}, \quad s_2(x,y) = \frac{1}{\sqrt{1 - \rho^2}} \left[ \frac{y - \mu_Y}{\sigma_Y} - \rho \frac{x - \mu_X}{\sigma_X} \right]
\]

### 3. Jacobian Determinant
To determine the pdf of \(X, Y\), we compute the Jacobian determinant:
\[
J = \det \begin{bmatrix} \frac{1}{\sigma_X} & 0 \\ \frac{\rho}{\sigma_Y \sqrt{1 - \rho^2}} & \frac{1}{\sigma_Y \sqrt{1 - \rho^2}} \end{bmatrix} = \frac{1}{\sigma_X \sigma_Y \sqrt{1 - \rho^2}}
\]

### 4. Joint Density Function
Using the Jacobian determinant, the joint density of \(X\) and \(Y\) is given by:
\[
f(x, y) = \frac{1}{2\pi \sigma_X \sigma_Y \sqrt{1 - \rho^2}} \exp \left[ -\frac{1}{2(1 - \rho^2)} \left( \frac{(x - \mu_X)^2}{\sigma_X^2} + \frac{(y - \mu_Y)^2}{\sigma_Y^2} - 2 \rho \frac{(x - \mu_X)(y - \mu_Y)}{\sigma_X \sigma_Y} \right) \right]
\]

### 5. Compact Matrix Representation
Since higher-dimensional joint densities of normals become increasingly complex, the bivariate normal density is often written in matrix form:
\[
\mathbf{x} = \begin{bmatrix} x \\ y \end{bmatrix}, \quad \boldsymbol{\mu} = \begin{bmatrix} \mu_X \\ \mu_Y \end{bmatrix}, \quad \boldsymbol{\Sigma} = \begin{bmatrix} \sigma_X^2 & \rho \sigma_X \sigma_Y \\ \rho \sigma_X \sigma_Y & \sigma_Y^2 \end{bmatrix}
\]
\[
f(\mathbf{x}) = \frac{1}{2\pi} (\det \boldsymbol{\Sigma})^{-1/2} \exp \left[ -\frac{1}{2} (\mathbf{x} - \boldsymbol{\mu})^T \boldsymbol{\Sigma}^{-1} (\mathbf{x} - \boldsymbol{\mu}) \right]
\]
To validate this form, we compute:
\[
(\det \boldsymbol{\Sigma})^{-1/2} = (\sigma_X^2 \sigma_Y^2 - \rho^2 \sigma_X^2 \sigma_Y^2)^{-1/2} = \frac{1}{\sigma_X \sigma_Y (1 - \rho^2)^{1/2}}
\]

### 6. Inverse Covariance Matrix Calculation
For a \(2 \times 2\) covariance matrix:
\[
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}, \quad A^{-1} = \frac{1}{ad - bc} \begin{bmatrix} d & -b \\ -c & a \end{bmatrix}
\]
Thus, applying this to \(\boldsymbol{\Sigma}\):
\[
(\mathbf{x} - \boldsymbol{\mu})^T \boldsymbol{\Sigma}^{-1} (\mathbf{x} - \boldsymbol{\mu}) = \frac{1}{1 - \rho^2} \left[ \frac{(x - \mu_X)^2}{\sigma_X^2} - 2 \rho \frac{(x - \mu_X)(y - \mu_Y)}{\sigma_X \sigma_Y} + \frac{(y - \mu_Y)^2}{\sigma_Y^2} \right]
\]
which confirms the earlier expression.

The transformation approach to deriving the bivariate normal density showcases how probability distributions change under one-to-one differentiable transformations. The use of Jacobians ensures that probability mass is preserved, and expressing the density in matrix form simplifies generalization to higher dimensions.

# Cholesky Decomposition and Bivariate Transformation

## Introduction
The Cholesky decomposition is a fundamental technique in linear algebra that is particularly useful in generating multivariate normal distributions. It allows us to transform independent standard normal variables into samples from a desired multivariate normal distribution.

### Cholesky Decomposition
The Cholesky decomposition applies to symmetric, positive-definite matrices. Given such a matrix \(X\), its Cholesky decomposition is:

\[
L = \text{Chol}(X)
\]

where \(L\) is a lower triangular matrix such that:

\[
LL^T = X.
\]

### Multiavariate Normal Distribution
A random vector \( X \in \mathbb{R}^n \) follows a multivariate normal distribution with mean vector \( \mu \) and covariance matrix \( \Sigma \):

\[
X \sim \mathcal{N}(\mu, \Sigma)
\]

This means that its probability density function (pdf) is given by:

\[
 f(X) = \frac{1}{(2\pi)^{n/2} |\Sigma|^{1/2}} \exp \left( -\frac{1}{2} (X - \mu)^T \Sigma^{-1} (X - \mu) \right).
\]

### Generating Samples using Cholesky Decomposition
To generate a sample \( X \sim \mathcal{N}(\mu, \Sigma) \), we start with a standard normal vector \( Z \sim \mathcal{N}(0, I) \), where \( Z \) is a vector of independent standard normal variables.

Using the Cholesky decomposition of \( \Sigma \), we obtain \( L \) such that:

\[
 \Sigma = LL^T.
\]

We then transform \( Z \) into \( X \) using:

\[
 X = \mu + LZ.
\]

This transformation ensures that \( X \) follows the desired multivariate normal distribution.

### Advantages of Cholesky Decomposition
- Efficient computation for positive definite covariance matrices.
- Ensures proper correlation structure in generated samples.
- Commonly used in Monte Carlo simulations and Bayesian statistics.

The Cholesky decomposition provides an elegant and computationally efficient method for sampling from a multivariate normal distribution. It transforms independent standard normal variables into correlated normal samples while preserving the desired covariance structure.

## Cholesky Decomposition
For any symmetric, positive-definite matrix \( \Sigma \), the Cholesky decomposition expresses \( \Sigma \) as:
\[
\Sigma = LL^T
\]
where \( L \) is a lower triangular matrix. This decomposition is instrumental in many applications, including Monte Carlo simulations and statistical modeling.

For the bivariate normal case, \( \Sigma \) is given by:
\[
\Sigma = \begin{bmatrix} \sigma_X^2 & \rho \sigma_X \sigma_Y \\ \rho \sigma_X \sigma_Y & \sigma_Y^2 \end{bmatrix}
\]
We need to find a lower triangular matrix \( L \) such that:
\[
L = \begin{bmatrix} a & 0 \\ b & c \end{bmatrix}
\]
Multiplying \( L \) by its transpose, we obtain the system of equations:
\[
\begin{aligned}
    a^2 &= \sigma_X^2 \\
    ab &= \rho \sigma_X \sigma_Y \\
    b^2 + c^2 &= \sigma_Y^2
\end{aligned}
\]
Solving for \( a, b, c \), we get:
\[
\begin{aligned}
    a &= \sigma_X \\
    b &= \rho \sigma_Y \\
    c &= \sigma_Y \sqrt{1 - \rho^2}
\end{aligned}
\]

## Bivariate Normal Transformation
Given two independent standard normal variables \( Z_1, Z_2 \sim \mathcal{N}(0,1) \), we can transform them into correlated normal variables \( X, Y \) using:
\[
\begin{bmatrix} X \\ Y \end{bmatrix} = \mu + L \begin{bmatrix} Z_1 \\ Z_2 \end{bmatrix}
\]
Expanding this, we obtain:
\[
\begin{aligned}
    X &= \mu_X + \sigma_X Z_1 \\
    Y &= \mu_Y + \sigma_Y [\rho Z_1 + \sqrt{1 - \rho^2}Z_2]
\end{aligned}
\]

This transformation shows how independent standard normal variables can be used to generate correlated normal variables, maintaining the specified mean vector \( \mu \) and covariance structure \( \Sigma \).

## Conditional Expectations and Variances
Given \( X \), the conditional expectation of \( Y \) is:
\[
E[Y|X=x] = \mu_Y + \sigma_Y \rho \frac{x - \mu_X}{\sigma_X}.
\]
Similarly, by symmetry:
\[
E[X|Y=y] = \mu_X + \sigma_X \rho \frac{y - \mu_Y}{\sigma_Y}.
\]
The conditional variances are given by:
\[
\text{Var}[Y|X=x] = \sigma_Y^2 (1 - \rho^2),
\]
\[
\text{Var}[X|Y=y] = \sigma_X^2 (1 - \rho^2).
\]
These results confirm that conditioning on one variable reduces the variance by a factor of \( (1 - \rho^2) \), highlighting the impact of correlation in a bivariate normal setting.

# Linear Combination of Random Variables

## Linear Combination
Given random variables \(X_1, X_2, \dots, X_p\) and constants \(c_1, c_2, \dots, c_p\), the expression:
\[
Y = c_1 X_1 + c_2 X_2 + \dots + c_p X_p
\]
is called a **linear combination** of \(X_1, X_2, \dots, X_p\).

## Mean of a Linear Function
If \( Y = c_1 X_1 + c_2 X_2 + \dots + c_p X_p \), then the expected value of \(Y\) is given by:
\[
E(Y) = c_1 E(X_1) + c_2 E(X_2) + \dots + c_p E(X_p)
\]

## Variance of a Linear Combination
If \(X_1, X_2, \dots, X_p\) are random variables, then the variance of their linear combination is:
\[
V(Y) = c_1^2 V(X_1) + c_2^2 V(X_2) + \dots + c_p^2 V(X_p) + 2 \sum_{i < j} c_i c_j \operatorname{cov}(X_i, X_j)
\]

If \(X_1, X_2, \dots, X_p\) are **independent**, the covariance terms vanish, simplifying to:
\[
V(Y) = c_1^2 V(X_1) + c_2^2 V(X_2) + \dots + c_p^2 V(X_p)
\]
> **Common mistake:** Forgetting to square the coefficients when computing variance.

## Expected Value of the Sample Mean
If we generate \(p\) observations from a distribution with mean \( \mu \), then:
\[
E(X_i) = \mu, \quad \text{for } i = 1,2,\dots,p.
\]
The sample mean is defined as:
\[
\bar{X} = \frac{X_1 + X_2 + \dots + X_p}{p} = \frac{1}{p}X_1 + \frac{1}{p}X_2 + \dots + \frac{1}{p}X_p
\]
Since \(\bar{X}\) is a linear combination of the observations, its expectation follows:
\[
E(\bar{X}) = \mu.
\]
> **Interpretation:** The expected value of the sample mean equals the population mean.

## Variance of the Sample Mean
If \(X_1, X_2, \dots, X_p\) are **independent** and have the same variance \(V(X_i) = \sigma^2\), then:
\[
V(\bar{X}) = \frac{\sigma^2}{p}.
\]
> **Interpretation:** The variance of the sample mean decreases as the number of observations \(p\) increases, meaning that averaging reduces variability.

# Reproductive Property of the Normal Distribution

## Linear Combination of Independent Normal Variables
One of the most important properties of the normal distribution is its **reproductive property**, which states that a linear combination of independent normal random variables is also normally distributed.

### Given:
Suppose \(X_1, X_2, \dots, X_p\) are independent normal random variables such that:
- \(X_i \sim N(\mu_i, \sigma_i^2)\), meaning each \(X_i\) follows a normal distribution with mean \(\mu_i\) and variance \(\sigma_i^2\).
- A linear combination of these variables is defined as:
  \[
  Y = c_1 X_1 + c_2 X_2 + \dots + c_p X_p,
  \]
  where \(c_1, c_2, \dots, c_p\) are constants.

### Result:
The random variable \(Y\) is also normally distributed with:
- **Mean**:
  \[
  \mu_Y = E(Y) = c_1 \mu_1 + c_2 \mu_2 + \dots + c_p \mu_p.
  \]
- **Variance**:
  \[
  \sigma_Y^2 = V(Y) = c_1^2 \sigma_1^2 + c_2^2 \sigma_2^2 + \dots + c_p^2 \sigma_p^2.
  \]
  Since the variables are independent, the covariance terms are zero, simplifying the variance computation.

Thus, we conclude:
\[
Y \sim N(\mu_Y, \sigma_Y^2).
\]

## Significance:
- This property is fundamental in statistical theory, particularly in linear regression, hypothesis testing, and Bayesian inference.
- It ensures that sums of independent normal variables remain normal, simplifying analytical derivations.
- The assumption of normality in many statistical models is justified because normal distributions are closed under linear transformation.

### Key Takeaway:
\[
\text{A linear combination of independent normal random variables is also normal.}
\]
