# One-Hot Encoding in Machine Learning

## 📌 What is One-Hot Encoding?
One-Hot Encoding is a technique used to convert **categorical variables** (text labels) into **numeric form** so that machine learning algorithms can process them.

It creates **binary columns** (0 or 1) for each category in the feature.

---

## 🔹 Example

Suppose we have a column `Color`:

| Color   |
|---------|
| Red     |
| Blue    |
| Green   |

After One-Hot Encoding:

| Color_Red | Color_Blue | Color_Green |
|-----------|------------|-------------|
| 1         | 0          | 0           |
| 0         | 1          | 0           |
| 0         | 0          | 1           |

---

## 🔹 Why Use One-Hot Encoding?
- Many ML models **cannot handle categorical data directly**.
- Prevents models from thinking there is an **order** between categories (unlike label encoding).
- Makes data suitable for algorithms like Logistic Regression, Decision Trees, Random Forest, etc.

---

## 🔹 When to Use?
- When you have **nominal categorical variables** (no ranking/order between values).
- Examples: Color, City, Country, Gender.

---

## 🔹 Python Example

```python
import pandas as pd

# Sample dataset
data = {'Color': ['Red', 'Blue', 'Green', 'Red']}
df = pd.DataFrame(data)

# Apply One-Hot Encoding
df_encoded = pd.get_dummies(df, columns=['Color'])

print(df_encoded)
