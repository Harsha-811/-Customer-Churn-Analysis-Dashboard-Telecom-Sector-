import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from google.colab import files
uploaded = files.upload()
df.head()
df.isnull().sum()
region_churn = df.groupby('Region')['Churn'].mean().sort_values(ascending=False)
print(region_churn)
df.groupby('Churn')['Engagement Score'].mean()
df.groupby('Churn')['Satisfaction Score'].mean()
df['Churn Risk Level'] = df['Churn'].apply(lambda x: 'High' if x == 1 else 'Low')

# Save to new CSV
df.to_csv("tableau_churn_data.csv", index=False)
from google.colab import files
files.download("tableau_churn_data.csv")
