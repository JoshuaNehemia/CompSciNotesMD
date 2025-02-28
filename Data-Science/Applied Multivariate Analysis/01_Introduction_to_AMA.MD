# Introduction to Applied Multivariate Analysis

## References
- **Applied Multivariate Statistical Analysis** by R.A. Johnson and D.W. Wichern, Sixth Edition, PHI, 2007.  
- **Multivariate Data Analysis** by Joseph F. Hair Jr, Rolph E. Anderson, Ronald L. Tatham, and William C. Black, Fifth Edition, Pearson Education, 2019.  
- **Principal Component Analysis** by I.T. Jolliffe, Second Edition, Springer, 2002.  

## Types of Variables (Stevens' Classification, 1951)
In statistical analysis, variables are classified based on their measurement properties:

- **Nominal** (Categorical)  
  - Represents distinct categories with no inherent order.  
  - Examples: Race, Religion, Counties, Sex.

- **Ordinal**  
  - Represents categories with a meaningful order but unequal intervals.  
  - Examples: Education levels, Health status, Smoking levels.

- **Interval**  
  - Represents numeric data with equal intervals but no true zero point.  
  - Examples: Temperature (Celsius/Fahrenheit), Time of day, Glucose blood levels.

- **Ratio**  
  - Similar to interval data but has a true zero point, allowing for meaningful ratios.  
  - Examples: Bone density, Weight, Height.

## Role of Variables in Data Analysis

- **Dependent Variable (Outcome, Response)**  
  - The variable being studied to see how it is affected by other factors.  
  - Example: Developing Coronary Heart Disease (CHD).

- **Independent Variable (Explanatory, Predictor)**  
  - The variable used to explain or predict changes in the dependent variable.  
  - Examples: Age, Sex, Diet, Exercise.

### Differences Between Dependent and Interdependent Variables

| Feature          | Dependent Variables                                   | Interdependent Variables                               |
|-----------------|-------------------------------------------------------|--------------------------------------------------------|
| **Definition**   | The variable you are trying to predict or explain. The outcome. | Variables that influence each other; reciprocal relationship. |
| **Relationship with other variables** | Influenced by other variables (independent or interdependent). | Influence each other; there's a feedback loop.         |
| **Causality**    | Thought to be *caused* or *affected* by other variables.    | Exhibit *mutual causation*; each variable is both a cause and an effect. |
| **Direction of Influence** | Unidirectional; influenced *by* other variables.         | Bidirectional; influence *and are influenced by* each other. |
| **Examples**      | Sales revenue (influenced by advertising), disease risk (influenced by lifestyle), student performance (influenced by teaching methods). | Supply and demand, inflation and unemployment, job satisfaction and employee performance. |
| **Analysis Techniques** | Regression analysis, ANOVA, etc. (depending on the model) | Simultaneous equation modeling, other specialized techniques for reciprocal relationships. |
| **Focus of Research** | Understanding how and why this variable changes.        | Understanding the dynamic interplay and feedback loops between these variables. |
| **Model Representation** | Often represented as the outcome variable in a model.    | Require models that explicitly account for their reciprocal relationships. |
| **Endogeneity** | Can be endogenous (if influenced by unmeasured factors). | Are inherently endogenous due to their mutual influence. |

### Differences Between Measurable and Latent Variables
- **Latent Constructs (Unobservable variables)**  
  - Abstract concepts that cannot be directly measured but are inferred from indicators.  
  - Examples: Socioeconomic status (SES), Satisfaction with health status.

- **Measurable Indicators**  
  - Observable variables used to quantify latent constructs.  
  - Examples: Education level, Employment status, Frequency of hospital visits, Miles walked.

| Feature          | Measurable Variables (Observed Variables/Manifest Variables) | Latent Variables (Unobserved Variables/Factors) |
|-----------------|-----------------------------------------------------------|---------------------------------------------------|
| **Definition**   | Directly measured or observed. The data you collect.      | Theoretical constructs inferred from measured variables. |
| **Observability** | Directly observable and quantifiable.                     | Not directly observable; inferred indirectly.      |
| **Examples**      | Height, weight, test scores, survey responses, sales.        | Intelligence, personality, customer satisfaction, brand loyalty. |
| **Role in Analysis** | Used as input for analysis; form the basis of the model.   | Represent underlying, unobservable phenomena; explain relationships between measured variables. |
| **Statistical Representation** | Represented by actual data values.                 | Represented by factors or constructs; estimated through statistical techniques. |
| **Measurement Error** | Measurement error is associated with the process of data collection. | Measurement error is related to how well the measured variables represent the latent construct (e.g., factor loadings). |
| **Complexity**   | Relatively simpler to understand and interpret.             | More complex; require statistical modeling to estimate and interpret. |
| **Purpose**       | To describe and quantify specific characteristics.           | To explain underlying relationships and simplify complex phenomena. |
| **Analysis Techniques** | Used in various statistical analyses (e.g., regression, ANOVA). | Used in factor analysis, structural equation modeling (SEM). |

## Data Types and Measures of Central Tendency
Different types of variables require different measures of central tendency:

- **Nominal** → Mode (Most frequently occurring category)
- **Ordinal** → Median (Middle value in ordered data)
- **Interval** → Mean (Arithmetic average)
- **Ratio** → Geometric Mean, Harmonic Mean (Used for multiplicative and rate-based data)


## Multivariate vs. Multivariable

The terms "multivariate" and "multivariable" are often used interchangeably, but they have distinct meanings. It's important to understand the difference, especially in the context of statistical methods.

*   **Multivariable:** This term refers to a situation where there are multiple *independent* variables. For example, in a study predicting crop yield based on rainfall and temperature, rainfall and temperature are the multivariable.
*   **Multivariate:** This term describes a situation where there are multiple *dependent* variables. For example, a study examining the effects of a drug on both blood pressure and heart rate is multivariate because it has two dependent variables.

A study can be both multivariable and multivariate if it involves multiple independent and multiple dependent variables.

## Classification of Multivariate Methods

Multivariate methods are statistical techniques used when dealing with multiple variables. These methods can be broadly classified based on the nature of the variables involved and the research objectives. One common classification is based on dependence:

### Dependence Methods (Explained in Detail)

Dependence methods are used when you want to understand how one or more variables (the *dependent* variables) are influenced or predicted by other variables (the *independent* variables).  The core idea is that there's a cause-and-effect (or at least a predictive) relationship you're trying to model.  These methods are categorized primarily by the number of dependent variables you're analyzing.

1.  **One Dependent Variable:**  This is the simplest case. You have a single outcome you're interested in explaining or predicting.

    *   **Metric Scale of Measure (Continuous Data):**  When your dependent variable is continuous (meaning it can take on a wide range of values, like height, weight, income, test scores, etc.), you use methods designed for this type of data.  **Multiple Regression** is the workhorse here.  It allows you to model the relationship between your single continuous dependent variable and *two or more* continuous (or sometimes carefully coded categorical) independent variables.  For example, you might use multiple regression to predict house prices (dependent variable) based on square footage, number of bedrooms, and location (independent variables).

    *   **Non-Metric Scale of Measure (Categorical Data):**  When your dependent variable is categorical (meaning it falls into distinct categories, like gender, diagnosis, political affiliation, product preference, etc.), you need different tools.

        *   **Discriminant Analysis:** This technique is used when you want to predict which category a data point belongs to based on its values on several continuous independent variables.  For example, you might use discriminant analysis to predict whether a customer will default on a loan (categories: yes/no) based on their credit score, income, and loan amount (continuous independent variables).

        *   **Linear Probability Models:**  These are a variation of regression where you try to predict a categorical (often binary/yes-no) outcome using regression techniques. While conceptually simpler, they have some statistical drawbacks and are sometimes less preferred than other methods like logistic regression (which is not listed here but is a common alternative).

2.  **Multiple Dependent Variables:** Now things get more complex.  You have *multiple* outcomes you want to analyze simultaneously.  This is where methods like MANOVA and Canonical Correlation come in.

    *   **Multivariate Analysis of Variance (MANOVA):**  MANOVA is like an extension of ANOVA (analysis of variance).  It's used when you want to compare group means on *multiple* dependent variables at the same time.  For example, you might want to compare the effects of different teaching methods (independent variable) on students' scores on both a math test and a reading test (two dependent variables).

    *   **Canonical Correlation:** This method explores the relationship between *two sets* of variables.  It tries to find the strongest correlations between linear combinations of the variables in each set.  For example, you might want to examine the relationship between a set of personality traits (e.g., extroversion, agreeableness) and a set of lifestyle choices (e.g., exercise frequency, diet).

3.  **Multiple Relationships of Dependent and Independent Variables:** This introduces the concept of more complex relationships.

    *   **Structural Equation Modeling (SEM):**  SEM is a very powerful and flexible technique that allows you to model complex relationships between multiple variables, including both direct and indirect effects.  It's often used when you have hypothesized causal relationships between variables and want to test those hypotheses.  It can handle both continuous and categorical variables.

### Interdependence Methods (Improved)

Interdependence methods are used when you're interested in exploring the relationships *among* a set of variables without assuming that some variables are dependent on others.  You're looking for the underlying structure and patterns in the data.

*   **Relationship Types:**

    *   **Variable Reduction:** These methods aim to simplify your data by reducing the number of variables while retaining as much information as possible.  **Factor Analysis** and **Principal Component Analysis (PCA)** fall into this category.

    *   **Clustering/Grouping:** These methods try to group similar data points (cases, objects) together based on their characteristics.  **Cluster Analysis** is the primary technique here.

    *   **Scaling and Visualization:**  These methods help you visualize the relationships between objects or variables in a lower-dimensional space.  **Multidimensional Scaling (MDS)** is a key example.

Interdependence methods are crucial in **exploratory data analysis (EDA)**.  They help you uncover hidden patterns, generate hypotheses, and gain a deeper understanding of your data before you move on to more formal modeling.

## 1. Regression Models
### Definition
Regression models are statistical tools used to analyze relationships between a dependent variable (response variable) and one or more independent variables (predictor variables). These models are primarily used for prediction, understanding patterns, and identifying influential variables. Regression models can be categorized into simple linear regression, multiple regression, logistic regression, and more advanced techniques like Cox proportional hazards models.

### Properties of Regression Models
- **Linearity**: Assumes that the relationship between the dependent and independent variables follows a straight-line trend.
- **Independence**: Observations should be independent of each other to avoid biases in estimation.
- **Homoscedasticity**: The variance of residuals (errors) remains constant across all levels of the independent variable.
- **Normality**: The error terms in the model follow a normal distribution, ensuring reliable parameter estimates.

## 2. Simple Linear Regression
A simple linear regression model is used when there is one independent variable and one dependent variable, represented as:
\[ Y = \beta_0 + \beta_1X + \epsilon \]
Where:
- \( Y \) = Dependent variable (target variable)
- \( X \) = Independent variable (predictor)
- \( \beta_0, \beta_1 \) = Regression coefficients (intercept and slope)
- \( \epsilon \) = Error term (random variation not captured by the model)

This model is used when we suspect a linear relationship between the predictor and target variables, such as predicting a student’s exam score based on study hours.

## 3. Correlation
### Definition
Correlation quantifies the strength and direction of the relationship between two numerical variables. It does not imply causation but provides insights into how two variables move together.

### Types of Correlation
- **Positive Correlation**: As one variable increases, the other also increases (e.g., income and expenditure).
- **Negative Correlation**: As one variable increases, the other decreases (e.g., exercise time and weight).
- **No Correlation**: No relationship between the two variables.

### Pearson Correlation Coefficient
The Pearson correlation coefficient (\( r \)) measures the linear relationship between two variables:
\[ r = \frac{\sum (X_i - \bar{X}) (Y_i - \bar{Y})}{\sqrt{\sum (X_i - \bar{X})^2 \sum (Y_i - \bar{Y})^2}} \]
Where \( -1 \leq r \leq 1 \), where:
- \( r = 1 \) indicates perfect positive correlation.
- \( r = -1 \) indicates perfect negative correlation.
- \( r = 0 \) indicates no linear relationship.

## 4. Negative Correlation
Negative correlation occurs when an increase in one variable results in a decrease in another. For example, as temperature increases, the number of winter clothing sales decreases.

## 5. Population Covariance
Covariance measures the extent to which two variables change together:
\[ \text{Cov}(X, Y) = \frac{1}{N} \sum_{i=1}^{N} (X_i - \bar{X})(Y_i - \bar{Y}) \]
A positive covariance indicates that the variables move in the same direction, whereas a negative covariance indicates an inverse relationship.

## 6. Regression Models Example
A practical example of regression is predicting house prices based on square footage:
\[ \text{Price} = \beta_0 + \beta_1(\text{Square Footage}) + \epsilon \]
Here, the square footage is the independent variable, and the price is the dependent variable.

## 7. Multiple Regression and Correlation
When more than one independent variable is used, the model extends to:
\[ Y = \beta_0 + \beta_1X_1 + \beta_2X_2 + ... + \beta_nX_n + \epsilon \]
This model allows for improved predictions by considering multiple influencing factors simultaneously.

## 8. Bivariate Regression Models
Bivariate regression models examine the relationship between two variables (one independent and one dependent), similar to simple linear regression but with a stronger focus on correlation strength.

## 9. Bivariate Regression Models Example
Example: Studying the impact of sleep hours on cognitive test scores.
\[ \text{Score} = \beta_0 + \beta_1(\text{Sleep Hours}) + \epsilon \]

## 10. Issues with Regression
Common challenges include:
- **Multicollinearity**: High correlation among independent variables leading to unreliable estimates.
- **Heteroscedasticity**: Unequal variance of errors causing inefficiencies in regression analysis.
- **Autocorrelation**: Error terms are correlated over time, violating independence.
- **Outliers**: Extreme values can disproportionately affect the regression model.

## 11. Canonical Correlation
Canonical correlation extends multiple regression to multivariate cases by analyzing relationships between two sets of variables.

## 12. Correlation Matrix
A correlation matrix displays pairwise correlation coefficients between multiple variables:
\[
\begin{bmatrix}
  1 & r_{12} & r_{13} \\
  r_{21} & 1 & r_{23} \\
  r_{31} & r_{32} & 1
\end{bmatrix}
\]

## 13. Discriminant Analysis
A statistical classification technique that separates data into predefined groups based on predictor variables.

## 14. Logistic Regression
Used for binary classification problems where the outcome is categorical (e.g., spam detection):
\[ P(Y=1) = \frac{e^{\beta_0 + \beta_1X}}{1 + e^{\beta_0 + \beta_1X}} \]

## 15. Survival Analysis (Event History Analysis)
Survival analysis studies time-to-event data, such as predicting machine failure times.

## 16. Log-Linear Regression
Used for modeling count data, particularly when response variables follow a Poisson distribution:
\[ \log(Y) = \beta_0 + \beta_1X_1 + ... + \beta_nX_n \]

## 17. Cox Proportional Hazards Model
A survival model expressing the hazard rate as:
\[ h(t) = h_0(t) e^{\beta_1X_1 + \beta_2X_2 + ... + \beta_nX_n} \]

## 18. Principal Component Analysis (PCA)
A technique used for dimensionality reduction by transforming correlated variables into uncorrelated principal components.

### Steps in PCA
1. Standardize the dataset.
2. Compute the covariance matrix.
3. Compute eigenvalues and eigenvectors.
4. Select the top principal components.
5. Transform the data into a new subspace.

## 19. Factor Analysis
### Definition
Factor analysis is a statistical method used to reduce a large number of observed variables into a smaller set of underlying factors that explain patterns in the data. It is commonly used in psychology, social sciences, and market research.

### Types of Factor Analysis
1. **Exploratory Factor Analysis (EFA)**: Used to uncover the underlying structure of a dataset without predefined hypotheses.
2. **Confirmatory Factor Analysis (CFA)**: Used to test predefined hypotheses and confirm whether a specific factor structure fits the data.

### Variable Characteristics in Factor Analysis
- **Observed Variables**: Measured directly.
- **Latent Variables**: Unobservable variables inferred from observed data.
- **Factor Loadings**: Represent the correlation between observed variables and underlying factors.

### Exploratory Factor Analysis (EFA)
EFA helps identify hidden structures in a dataset by:
1. Identifying how variables cluster together.
2. Reducing dimensionality while preserving variance.
3. Using techniques such as principal component extraction and varimax rotation.

### Confirmatory Factor Analysis (CFA)
CFA validates predefined factor structures by:
1. Testing hypothesis-driven models.
2. Using fit indices (e.g., RMSEA, CFI, TLI) to evaluate model fit.
3. Refining constructs in psychological and behavioral research.

## 20. Clustering and Discriminant Analysis
### Clustering Analysis
Clustering groups similar data points together based on intrinsic patterns. Common clustering methods include:
- **K-Means Clustering**: Partitions data into K clusters based on similarity.
- **Hierarchical Clustering**: Builds a tree-like structure to define data groupings.
- **DBSCAN**: Identifies clusters based on density distribution.

### Discriminant Analysis
Discriminant analysis is a classification technique that separates observations into predefined groups using predictor variables. It is widely used in:
- Medical diagnosis (e.g., distinguishing between diseases).
- Customer segmentation (e.g., classifying customer preferences).
- Fraud detection (e.g., identifying fraudulent transactions).



