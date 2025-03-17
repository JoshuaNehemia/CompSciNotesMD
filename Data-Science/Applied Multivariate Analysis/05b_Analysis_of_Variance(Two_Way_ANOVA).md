# Two-Way ANOVA

Two-Way ANOVA (Analysis of Variance) is a **statistical test** used to analyze the effect of **two independent categorical factors** on a continuous dependent variable **simultaneously**. It determines:
1. The individual effects of each factor (**main effects**).
2. Whether the two factors interact and influence the dependent variable together (**interaction effect**).

### **Example of Two-Way ANOVA**
Suppose you want to analyze the effect of **diet type** (Factor A) and **exercise type** (Factor B) on **weight loss** (dependent variable). Two-Way ANOVA helps determine:
- Whether **diet type** alone influences weight loss (**main effect of Factor A**).
- Whether **exercise type** alone influences weight loss (**main effect of Factor B**).
- Whether there is an **interaction** between diet and exercise (e.g., some diets work better with specific exercises but not others).

---

## **Differences Between One-Way and Two-Way ANOVA**
| Feature  | **One-Way ANOVA** | **Two-Way ANOVA** |
|----------|------------------|------------------|
| **Number of Independent Variables (Factors)** | 1 factor | 2 factors |
| **Number of Hypotheses Tested** | 1 (effect of the factor) | 3 (effect of Factor A, effect of Factor B, and interaction effect) |
| **Example Scenario** | Effect of different teaching methods on student scores | Effect of teaching methods and class sizes on student scores |
| **Interaction Effect Considered?** | ❌ No | ✅ Yes |
| **Complexity** | Simpler | More complex but provides more insights |

---

## **Why Does Two-Way ANOVA Exist?**
Two-Way ANOVA exists because **real-world data often involve multiple factors that influence the outcome simultaneously**. Using only One-Way ANOVA could lead to **misinterpretation** because it does not account for interactions between factors.

### **Advantages of Two-Way ANOVA:**
1. **Detects Interactions** – It shows whether two factors work **independently or interact** to influence the outcome.
2. **More Statistical Power** – It reduces the risk of **Type I errors** (false positives) by analyzing both factors together instead of running multiple One-Way ANOVAs.
3. **More Realistic** – Most experiments involve multiple factors, making Two-Way ANOVA a better reflection of real-world situations.

### **Example of Interaction:**
- Suppose we study the effect of **coffee consumption** and **sleep duration** on **reaction time**.
- If we only use One-Way ANOVA, we might conclude that coffee **always** improves reaction time.
- But with Two-Way ANOVA, we might discover an **interaction effect**, showing that coffee **only improves reaction time for sleep-deprived individuals but not for well-rested individuals**.

---

**Use One-Way ANOVA** when analyzing the effect of **one** factor on a dependent variable.
**Use Two-Way ANOVA** when you suspect **two factors** influence the dependent variable, especially if you think they might **interact**.

## **Two-Way ANOVA Table**  

A **Two-Way ANOVA table** is similar to a One-Way ANOVA table but includes additional components to account for the second factor and their interaction. The table decomposes the total variation in the data into contributions from **two independent factors, their interaction, and error**.

---

### **General Structure of a Two-Way ANOVA Table**  

| Source of Variation | Sum of Squares (SS) | Degrees of Freedom (df) | Mean Square (MS) | F-Statistic (F) |  
|--------------------|-------------------|-----------------|---------------|-------------|  
| Factor A (Main Effect) | \( SS_A \) | \( df_A = a - 1 \) | \( MS_A = SS_A / df_A \) | \( F_A = MS_A / MS_E \) |  
| Factor B (Main Effect) | \( SS_B \) | \( df_B = b - 1 \) | \( MS_B = SS_B / df_B \) | \( F_B = MS_B / MS_E \) |  
| Interaction (A × B) | \( SS_{AB} \) | \( df_{AB} = (a - 1)(b - 1) \) | \( MS_{AB} = SS_{AB} / df_{AB} \) | \( F_{AB} = MS_{AB} / MS_E \) |  
| Error (Residual) | \( SS_E \) | \( df_E = ab(n - 1) \) | \( MS_E = SS_E / df_E \) | - |  
| **Total** | \( SS_{TO} \) | \( df_{TO} = N - 1 \) | - | - |  

Where:  
- \( a \) = Number of levels in Factor A  
- \( b \) = Number of levels in Factor B  
- \( n \) = Number of replicates per combination  
- \( N \) = Total number of observations  
- \( SS \) = Sum of Squares (measures variation)  
- \( df \) = Degrees of Freedom (number of independent values)  
- \( MS \) = Mean Square (variation per degree of freedom)  
- \( F \) = Test statistic for hypothesis testing  

---

### **Understanding Each Component**
1. **Factor A (SS_A, df_A, MS_A, F_A)**  
   - Measures how much variation is due to **Factor A alone**.  
   - Example: If Factor A is **teaching method**, this tests whether different methods significantly affect student scores.  

2. **Factor B (SS_B, df_B, MS_B, F_B)**  
   - Measures variation due to **Factor B alone**.  
   - Example: If Factor B is **classroom size**, this tests whether different sizes significantly affect scores.  

3. **Interaction Effect (SS_AB, df_AB, MS_AB, F_AB)**  
   - Measures whether the two factors **interact** with each other.  
   - Example: Does the **effect of teaching method** depend on the **classroom size**?  

4. **Error (Residual) (SS_E, df_E, MS_E)**  
   - Represents **unexplained variability** in the data.  
   - It accounts for **random errors** or **individual differences**.  

5. **Total Variation (SS_TO, df_TO)**  
   - The sum of all variations in the dataset.  
   - \( SS_{TO} = SS_A + SS_B + SS_{AB} + SS_E \)  

---

### **Key Differences Between One-Way and Two-Way ANOVA Tables**
| Feature | One-Way ANOVA | Two-Way ANOVA |
|---------|-------------|-------------|
| **Factors Analyzed** | 1 factor | 2 factors + interaction |
| **Sources of Variation** | Treatment, Error, Total | Factor A, Factor B, Interaction, Error, Total |
| **Degrees of Freedom** | \( df_T = a - 1 \), \( df_E = N - a \) | \( df_A = a - 1 \), \( df_B = b - 1 \), \( df_{AB} = (a-1)(b-1) \), \( df_E = ab(n-1) \) |

---

### **Interpretation of Two-Way ANOVA Results**
- If **Factor A is significant** (\( p < 0.05 \)): Factor A affects the dependent variable.  
- If **Factor B is significant** (\( p < 0.05 \)): Factor B affects the dependent variable.  
- If **Interaction is significant** (\( p < 0.05 \)): Factor A and B influence the dependent variable **together**, meaning their effects depend on each other.  

### **Calculate the p-Value in Two-Way ANOVA**  
The **p-value** in Two-Way ANOVA is used to determine whether the effects of the factors and their interaction are statistically significant. The p-values are obtained from the **F-statistic** calculated for each factor and their interaction.


### **Steps to Calculate the p-Value for Two-Way ANOVA**
1. **Compute the Sum of Squares (SS)**  
   - \( SS_A \) for Factor A  
   - \( SS_B \) for Factor B  
   - \( SS_{AB} \) for Interaction (A × B)  
   - \( SS_E \) for Error  

2. **Compute Degrees of Freedom (df)**  
   - \( df_A = a - 1 \)  
   - \( df_B = b - 1 \)  
   - \( df_{AB} = (a - 1)(b - 1) \)  
   - \( df_E = ab(n - 1) \)  

3. **Calculate Mean Squares (MS)**  
   - \( MS_A = SS_A / df_A \)  
   - \( MS_B = SS_B / df_B \)  
   - \( MS_{AB} = SS_{AB} / df_{AB} \)  
   - \( MS_E = SS_E / df_E \)  

4. **Compute the F-statistic**  
   - \( F_A = MS_A / MS_E \)  
   - \( F_B = MS_B / MS_E \)  
   - \( F_{AB} = MS_{AB} / MS_E \)  

5. **Find the p-Value from the F-Distribution**  
   - Use an **F-table** or statistical software (Python, R, Excel, etc.)  
   - The p-value is the probability of obtaining an F-statistic as extreme as the one calculated **under the null hypothesis**  
   - If \( p < 0.05 \), the effect is statistically significant  

### **How to Check for Interaction Between Two Factors?**  
The interaction term **\( SS_{AB} \)** tests whether the effect of one factor depends on the level of the other factor.

#### **1. Compute the Interaction F-Statistic**
\[
F_{AB} = \frac{MS_{AB}}{MS_E}
\]
- If \( F_{AB} \) is large, it suggests a possible interaction.

#### **2. Find the p-Value for the Interaction**
- Use the **F-distribution** to find the probability that the observed \( F_{AB} \) is due to chance.
- If **p-value for interaction < 0.05**, then **Factor A and Factor B interact significantly**.

#### **3. Interpret the Interaction**
- **Significant Interaction (\( p < 0.05 \))**  
  - The effect of one factor **depends on** the level of the other factor.  
  - Example: Teaching method effectiveness **varies based on** classroom size.  
- **No Significant Interaction (\( p > 0.05 \))**  
  - The two factors are **independent** of each other.  
  - Example: Teaching method affects performance **regardless of** classroom size.

---

### **Example Calculation Using Python**
You can calculate the p-values for Two-Way ANOVA using Python (`statsmodels`):

```python
import pandas as pd
import statsmodels.api as sm
from statsmodels.formula.api import ols

# Sample data
df = pd.DataFrame({
    'Factor_A': ['A1', 'A1', 'A2', 'A2', 'A1', 'A2', 'A1', 'A2'],
    'Factor_B': ['B1', 'B2', 'B1', 'B2', 'B1', 'B2', 'B2', 'B1'],
    'Response': [10, 15, 12, 18, 11, 19, 14, 16]
})

# Perform Two-Way ANOVA
model = ols('Response ~ C(Factor_A) + C(Factor_B) + C(Factor_A):C(Factor_B)', data=df).fit()
anova_table = sm.stats.anova_lm(model, typ=2)

print(anova_table)  # Shows SS, df, F-statistic, and p-values
```
This will output the p-values for Factor A, Factor B, and their interaction.

---


