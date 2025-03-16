#### **1. Trivariate Normal Distribution**
- **Contour Map**: The contour map of a trivariate normal distribution is defined by the equation:
  \[
  (\bar{x} - \bar{\mu})' \Sigma^{-1} (\bar{x} - \bar{\mu}) = \text{constant}
  \]
  where:
  - \(\bar{x}\) is the vector of variables.
  - \(\bar{\mu}\) is the mean vector.
  - \(\Sigma\) is the covariance matrix.

- **Visualization**: The trivariate normal distribution can be visualized in 3D space, with axes \(x_1\), \(x_2\), and \(x_3\).

---

#### **2. Marginal and Conditional Distributions**
- **Marginal Distribution**:
  - For a multivariate normal distribution, the marginal distribution of any subset of variables is also multivariate normal.
  - If \(\bar{x} = \begin{bmatrix} \bar{x}_1 \\ \bar{x}_2 \end{bmatrix}\) is multivariate normal with mean \(\bar{\mu}\) and covariance \(\Sigma\), then:
    - \(\bar{x}_1\) is multivariate normal with mean \(\bar{\mu}_1\) and covariance \(\Sigma_{11}\).
    - \(\bar{x}_2\) is multivariate normal with mean \(\bar{\mu}_2\) and covariance \(\Sigma_{22}\).

- **Conditional Distribution**:
  - The conditional distribution of \(\bar{x}_1\) given \(\bar{x}_2\) is also multivariate normal with:
    - **Mean**: 
      \[
      \bar{\mu}_{1|2} = \bar{\mu}_1 + \Sigma_{12} \Sigma_{22}^{-1} (\bar{x}_2 - \bar{\mu}_2)
      \]
    - **Covariance**:
      \[
      \Sigma_{11|2} = \Sigma_{11} - \Sigma_{12} \Sigma_{22}^{-1} \Sigma_{12}'
      \]

---

#### **3. Independence in Multivariate Normal Distribution**
- **Independence Condition**:
  - Two vectors \(\bar{x}_1\) and \(\bar{x}_2\) are independent if and only if \(\Sigma_{12} = 0\) (i.e., the off-diagonal blocks of the covariance matrix are zero).
- **Component Independence**:
  - The components of \(\bar{x}\) are independent if the covariance matrix \(\Sigma\) is diagonal (i.e., \(\sigma_{ij} = 0\) for all \(i \neq j\)).

---

#### **4. Transformations of Random Variables**
- **General Transformation**:
  - If \(\bar{x}\) is a random vector with joint density \(f(\bar{x})\), and \(\bar{u} = h(\bar{x})\) is an invertible transformation, then the joint density of \(\bar{u}\) is:
    \[
    g(\bar{u}) = f(\bar{x}) |J|
    \]
    where \(J\) is the Jacobian of the transformation:
    \[
    J = \frac{d(\bar{x})}{d(\bar{u})}
    \]

- **Linear Transformations**:
  - If \(\bar{u} = A\bar{x} + \bar{c}\), where \(A\) is an invertible matrix, then:
    \[
    g(\bar{u}) = f(A^{-1}(\bar{u} - \bar{c})) \frac{1}{|A|}
    \]
  - The transformed vector \(\bar{u}\) is also multivariate normal with:
    - **Mean**: \(A\bar{\mu} + \bar{c}\)
    - **Covariance**: \(A\Sigma A'\)

---

#### **5. Partial Covariance and Correlation**
- **Partial Covariance**:
  - The partial covariance between two variables \(x_i\) and \(x_j\), given a set of variables, is defined as:
    \[
    \sigma_{ij|1,2,\dots,q} = \sigma_{ij} - \Sigma_{12} \Sigma_{22}^{-1} \Sigma_{12}'
    \]
    - This measures the covariance between \(x_i\) and \(x_j\) after removing the effect of the other variables.

- **Partial Correlation**:
  - The partial correlation between \(x_i\) and \(x_j\) is:
    \[
    \rho_{ij|1,2,\dots,q} = \frac{\sigma_{ij|1,2,\dots,q}}{\sqrt{\sigma_{ii|1,2,\dots,q}} \sqrt{\sigma_{jj|1,2,\dots,q}}}
    \]
    - This measures the linear relationship between \(x_i\) and \(x_j\) after controlling for the other variables.

---

#### **6. Regression Coefficients in Multivariate Normal**
- **Matrix of Regression Coefficients**:
  - The matrix \(B = \Sigma_{12}' \Sigma_{11}^{-1}\) is used to predict \(\bar{x}_2\) from \(\bar{x}_1\).
  - The conditional mean of \(\bar{x}_2\) given \(\bar{x}_1\) is:
    \[
    \bar{\mu}_{2|1} = B\bar{x}_1 + \bar{\alpha}
    \]
    where \(\bar{\alpha} = \bar{\mu}_2 - \Sigma_{12}' \Sigma_{11}^{-1} \bar{\mu}_1\).

---

#### **7. Example: Conditional Distribution**
- **Given**:
  - A 4-variate normal distribution with mean vector \(\bar{\mu}\) and covariance matrix \(\Sigma\).
- **Find**:
  - The conditional distribution of \(\bar{x}_2 = \begin{bmatrix} x_3 \\ x_4 \end{bmatrix}\) given \(\bar{x}_1 = \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}\).
- **Solution**:
  - Compute the conditional mean and covariance using the formulas:
    \[
    \bar{\mu}_{2|1} = \bar{\mu}_2 + \Sigma_{12} \Sigma_{11}^{-1} (\bar{x}_1 - \bar{\mu}_1)
    \]
    \[
    \Sigma_{22|1} = \Sigma_{22} - \Sigma_{12} \Sigma_{11}^{-1} \Sigma_{12}'
    \]

---

#### **8. Independence and Zero Correlation**
- **Zero Correlation Implies Independence**:
  - In a multivariate normal distribution, if the correlation \(\rho = 0\), then the variables are independent.
- **Implications**:
  - If \(\Sigma_{12} = 0\), then \(\bar{x}_1\) and \(\bar{x}_2\) are independent.

---

#### **9. Summary of Key Results**
- **Marginal Distribution**:
  - The marginal distribution of any subset of variables in a multivariate normal distribution is also multivariate normal.
- **Conditional Distribution**:
  - The conditional distribution of a subset of variables given another subset is multivariate normal.
- **Transformations**:
  - Linear transformations of multivariate normal variables result in multivariate normal distributions.
- **Independence**:
  - Variables are independent if their covariance is zero.


Here’s a **combined and polished set of notes** for **pages 92-100**, with all equations in **LaTeX format** and organized into a clear, structured format:

---

### PROOF

---

#### **1. Joint Density of Multivariate Normal Distribution**

The joint density of the random vector \(\bar{x} = \begin{bmatrix} \bar{x}_1 \\ \bar{x}_2 \end{bmatrix}\) is given by:

\[
f(\bar{x}) = f(\bar{x}_1, \bar{x}_2) = \frac{1}{(2\pi)^{p/2} |\Sigma|^{\frac{1}{2}}} e^{-\frac{1}{2} (\bar{x} - \bar{\mu})' \Sigma^{-1} (\bar{x} - \bar{\mu})}
\]

where:
- \(\bar{\mu} = \begin{bmatrix} \bar{\mu}_1 \\ \bar{\mu}_2 \end{bmatrix}\) is the mean vector.
- \(\Sigma = \begin{bmatrix} \Sigma_{11} & \Sigma_{12} \\ \Sigma_{12}' & \Sigma_{22} \end{bmatrix}\) is the covariance matrix.

---

#### **2. Inverse of the Covariance Matrix**

The inverse of the covariance matrix \(\Sigma\) is:

\[
\Sigma^{-1} = \begin{bmatrix} \Sigma^{11} & \Sigma^{12} \\ \Sigma^{21} & \Sigma^{22} \end{bmatrix}
\]

where:
\[
\Sigma^{11} = \Sigma_{11}^{-1} + \Sigma_{11}^{-1} \Sigma_{12} \Sigma_{22 \cdot 1}^{-1} \Sigma_{12}' \Sigma_{11}^{-1}
\]
\[
\Sigma^{12} = -\Sigma_{11}^{-1} \Sigma_{12} \Sigma_{22 \cdot 1}^{-1}
\]
\[
\Sigma^{21} = -\Sigma_{22 \cdot 1}^{-1} \Sigma_{12}' \Sigma_{11}^{-1}
\]
\[
\Sigma^{22} = \Sigma_{22 \cdot 1}^{-1}
\]

and:
\[
\Sigma_{22 \cdot 1} = \Sigma_{22} - \Sigma_{12}' \Sigma_{11}^{-1} \Sigma_{12}
\]

---

#### **3. Quadratic Form in the Exponent**

The quadratic form in the exponent of the joint density is:

\[
Q(\bar{x}_1, \bar{x}_2) = (\bar{x} - \bar{\mu})' \Sigma^{-1} (\bar{x} - \bar{\mu})
\]

Expanding this, we get:
\[
Q(\bar{x}_1, \bar{x}_2) = (\bar{x}_1 - \bar{\mu}_1)' \Sigma_{11}^{-1} (\bar{x}_1 - \bar{\mu}_1) + (\bar{x}_2 - \bar{\mu}_2 + \Sigma_{12}' \Sigma_{11}^{-1} (\bar{x}_1 - \bar{\mu}_1))' \Sigma_{22 \cdot 1}^{-1} (\bar{x}_2 - \bar{\mu}_2 + \Sigma_{12}' \Sigma_{11}^{-1} (\bar{x}_1 - \bar{\mu}_1))
\]

---

#### **4. Marginal Distribution**

The marginal distribution of \(\bar{x}_1\) is:

\[
f_1(\bar{x}_1) = \frac{1}{(2\pi)^{q/2} |\Sigma_{11}|^{\frac{1}{2}}} e^{-\frac{1}{2} (\bar{x}_1 - \bar{\mu}_1)' \Sigma_{11}^{-1} (\bar{x}_1 - \bar{\mu}_1)}
\]

---

#### **5. Conditional Distribution**

The conditional distribution of \(\bar{x}_2\) given \(\bar{x}_1\) is:

\[
f_{2|1}(\bar{x}_2 | \bar{x}_1) = \frac{1}{(2\pi)^{(p-q)/2} |\Sigma_{22 \cdot 1}|^{\frac{1}{2}}} e^{-\frac{1}{2} (\bar{x}_2 - \bar{b})' \Sigma_{22 \cdot 1}^{-1} (\bar{x}_2 - \bar{b})}
\]

where:
\[
\bar{b} = \bar{\mu}_2 + \Sigma_{12}' \Sigma_{11}^{-1} (\bar{x}_1 - \bar{\mu}_1)
\]
\[
\Sigma_{22 \cdot 1} = \Sigma_{22} - \Sigma_{12}' \Sigma_{11}^{-1} \Sigma_{12}
\]

---

#### **6. Matrix of Partial Variances and Covariances**

The matrix of partial variances and covariances is:

\[
\Sigma_{22 \cdot 1} = \Sigma_{22} - \Sigma_{12}' \Sigma_{11}^{-1} \Sigma_{12}
\]

The \((i, j)\)-th element of this matrix is the **partial covariance** between \(x_i\) and \(x_j\) given \(\bar{x}_1\):

\[
\sigma_{ij \cdot 1, 2, \dots, q} = \sigma_{ij} - \Sigma_{12} \Sigma_{22}^{-1} \Sigma_{12}'
\]

---

#### **7. Partial Correlation**

The **partial correlation** between \(x_i\) and \(x_j\) given \(\bar{x}_1\) is:

\[
\rho_{ij \cdot 1, 2, \dots, q} = \frac{\sigma_{ij \cdot 1, 2, \dots, q}}{\sqrt{\sigma_{ii \cdot 1, 2, \dots, q}} \sqrt{\sigma_{jj \cdot 1, 2, \dots, q}}}
\]

---

#### **8. Regression Coefficients**

The matrix of regression coefficients for predicting \(\bar{x}_2\) from \(\bar{x}_1\) is:

\[
B = \Sigma_{12}' \Sigma_{11}^{-1}
\]

The conditional mean of \(\bar{x}_2\) given \(\bar{x}_1\) is:

\[
\bar{\mu}_{2|1} = B \bar{x}_1 + \bar{\alpha}
\]

where:
\[
\bar{\alpha} = \bar{\mu}_2 - \Sigma_{12}' \Sigma_{11}^{-1} \bar{\mu}_1
\]

---

#### **9. Independence in Multivariate Normal Distribution**

Two vectors \(\bar{x}_1\) and \(\bar{x}_2\) are independent if and only if:

\[
\Sigma_{12} = 0
\]

If \(\Sigma_{12} = 0\), then:
\[
f(\bar{x}_1, \bar{x}_2) = f_1(\bar{x}_1) f_2(\bar{x}_2)
\]



1. **Joint Density**: The joint density of a multivariate normal distribution is defined by its mean vector \(\bar{\mu}\) and covariance matrix \(\Sigma\).
2. **Marginal Distribution**: The marginal distribution of any subset of variables is also multivariate normal.
3. **Conditional Distribution**: The conditional distribution of a subset of variables given another subset is multivariate normal.
4. **Partial Covariance and Correlation**: These measure the relationship between variables after controlling for other variables.
5. **Regression Coefficients**: Used to predict one subset of variables from another.
6. **Independence**: Variables are independent if their covariance is zero.
