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
<img width="1642" height="572" alt="image" src="https://github.com/user-attachments/assets/d6b4cf9f-b0e0-4519-9393-3d7f64ec937e" />

CODING
df.info()

OUTPUT
<img width="537" height="468" alt="image" src="https://github.com/user-attachments/assets/f1f1f1a2-7568-4c95-a448-d5192801c804" />

CODING
df.dtypes

OUTPUT 
<img width="342" height="620" alt="image" src="https://github.com/user-attachments/assets/f07c8ff7-5633-4ebb-8bc5-ddd012925701" />

CODING
df.value_counts()

OUTPUT
<img width="1687" height="660" alt="image" src="https://github.com/user-attachments/assets/0b6ab747-4629-46a7-a4db-58eca11c8329" />

CODING
df['Age'].value_counts()

OUTPUT
<img width="270" height="660" alt="image" src="https://github.com/user-attachments/assets/55784a4f-7efb-4a16-aaa4-775b2e1ec3ff" />

CODING
df.shape

OUTPUT
<img width="175" height="57" alt="image" src="https://github.com/user-attachments/assets/b21e7b56-b2ce-4c54-b202-6b6c25d7c372" />

CODING
df.set_index("PassengerId",inplace=True)
df.describe()

OUTPUT
<img width="965" height="415" alt="image" src="https://github.com/user-attachments/assets/2b4498db-5554-4f9f-8bb1-2ba4cc1aeb3e" />

CODING
df.nunique()

OUTPUT
<img width="351" height="582" alt="image" src="https://github.com/user-attachments/assets/f505aebe-4bf9-4d2e-b3da-cfe6ebedf5dd" />

CODING
sns.countplot(data=df,x="Survived")

OUTPUT
<img width="882" height="623" alt="image" src="https://github.com/user-attachments/assets/9df6efdc-247d-4f22-8d08-9ec19666f669" />

CODING
df.Pclass.unique()

OUTPUT
<img width="257" height="47" alt="image" src="https://github.com/user-attachments/assets/09c47471-9701-4673-841f-a8f4e91d007d" />

CODING
df.rename(columns={'Sex':'Gender'},inplace=True)
df

OUTPUT
<img width="1271" height="517" alt="image" src="https://github.com/user-attachments/assets/871b9a9a-ef0a-4456-8ba2-6812c39e4937" />

CODING
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)

OUTPUT
<img width="1050" height="712" alt="image" src="https://github.com/user-attachments/assets/cc3e1918-1ef1-4f13-9cbc-71da5746e57b" />

CODING
df.boxplot(column="Age",by="Survived")

OUTPUT
<img width="840" height="666" alt="image" src="https://github.com/user-attachments/assets/1cc9dcac-ad38-4825-8ead-c639b935ec1b" />

CODING
sns.scatterplot(x=df["Age"],y=df["Fare"])

OUTPUT
<img width="868" height="635" alt="image" src="https://github.com/user-attachments/assets/c71d3bd0-036f-4b97-abbd-00ad9da10f6e" />

CODING
fig, ax1 =plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)


OUTPUT
<img width="1045" height="627" alt="image" src="https://github.com/user-attachments/assets/f0d86708-e64e-4f24-ae73-5e40e5cf2d25" />

CODING
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")

OUTPUT
<img width="1547" height="703" alt="image" src="https://github.com/user-attachments/assets/185bb7aa-8557-44dc-b437-1fdbd30d8cbf" />

CODING
corr = df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)


OUTPUT
<img width="796" height="613" alt="image" src="https://github.com/user-attachments/assets/1380b4f9-830d-4bab-ade7-f8b1bd584fad" />















# RESULT
    Thus the dataset value is found
