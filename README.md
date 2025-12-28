# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
        <<INCLUDE YOUR CODING AND OUTPUT SCREENSHOTS>>
        import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df


OUTPUT
<img width="1642" height="572" alt="image" src="https://github.com/user-attachments/assets/94c63b78-0ea0-42f7-9d6b-9755fcb7dd97" />

# CODING
df.info()

# OUTPUT
<img width="537" height="468" alt="image" src="https://github.com/user-attachments/assets/da5e6a6b-c9e8-4605-bf33-2603d959090e" />

# CODING
df.dtypes

# OUTPUT
<img width="342" height="620" alt="image" src="https://github.com/user-attachments/assets/a7531b2a-1ac1-48fe-bb23-472065e3c370" />

# CODING
df.value_counts()

# OUPUT
<img width="270" height="660" alt="image" src="https://github.com/user-attachments/assets/219926e4-7f18-42db-8fee-c08b3e17bd1a" />

# CODING
df.shape

# OUTPUT
<img width="175" height="57" alt="image" src="https://github.com/user-attachments/assets/720247a1-c31f-403e-bca7-6bb1a50b4531" />

# CODING
df.set_index("PassengerId",inplace=True)
df.describe()

# OUTPUT
<img width="965" height="415" alt="image" src="https://github.com/user-attachments/assets/f7b034d4-fa05-4dd7-801c-0b4bb0f63fe9" />

# CODING
df.nunique()

# OUTPUT
<img width="351" height="582" alt="image" src="https://github.com/user-attachments/assets/28a7682f-88f6-4a94-8d59-db1ed406a2e9" />

# CODING
sns.countplot(data=df,x="Survived")

# OUTPUT
<img width="882" height="623" alt="image" src="https://github.com/user-attachments/assets/b878a292-52b9-46e2-b86d-449a400b3da6" />

# CODING
df.Pclass.unique()

# OUTPUT
<img width="257" height="47" alt="image" src="https://github.com/user-attachments/assets/fd6b11b2-179c-4499-adba-c4ddc7d84815" />

# CODING
df.rename(columns={'Sex':'Gender'},inplace=True)
df

# OUTPUT
<img width="1271" height="517" alt="image" src="https://github.com/user-attachments/assets/08ede257-03ca-440c-8470-2d138e927d84" />

# CODING
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)

# OUTPUT
<img width="1050" height="712" alt="image" src="https://github.com/user-attachments/assets/155367c6-211a-4cb9-9f4d-d6d1cb60f446" />

# CODING
df.boxplot(column="Age",by="Survived")

# OUTPUT
<img width="840" height="666" alt="image" src="https://github.com/user-attachments/assets/be9e2ff0-08f8-4d09-9cfe-a53d58190121" />

# CODING
sns.scatterplot(x=df["Age"],y=df["Fare"])

# OUTPUT
<img width="868" height="635" alt="image" src="https://github.com/user-attachments/assets/948b379a-04fa-41bd-9609-af6c56fe48b2" />

# CODING
fig, ax1 =plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)

# OUTPUT
<img width="1045" height="627" alt="image" src="https://github.com/user-attachments/assets/723228bf-dd8b-43b0-abca-b1dfab86fa3e" />

# CODING
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")

# OUTPUT
<img width="1547" height="703" alt="image" src="https://github.com/user-attachments/assets/930d7b33-e67b-4aab-8a3c-6dcee76ba87f" />

# CODING
corr = df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)

# OUTPUT
<img width="796" height="613" alt="image" src="https://github.com/user-attachments/assets/b9696b6e-3102-4efb-976b-7abf387d1b07" />

# RESULT
        <<INCLUDE YOUR RESULT HERE>>
            Thus the dataset value is found
