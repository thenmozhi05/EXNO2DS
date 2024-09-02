# EXNO2DS-Exploratory Data Analysis
## AIM:
  To perform Exploratory Data Analysis on the given data set.
      
## EXPLANATION:
 The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
## ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
### Developed by: thenmozhi p
### Register no: 212223100059
```py
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns  
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/6499f6f0-5776-493f-9cfe-43140a7c35f6)

```py
df.info()
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/5d93e91f-94a8-42b8-97af-9c9716ebe3f8)

```py
df.shape
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/380bbd5e-3463-437e-955b-3b35ddd89640)

```py
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/6a4e6b50-8a3c-43ae-bd1c-5a82bb1b7b4b)

```py
df.shape
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/d489f8ff-b5ff-4a6e-a312-307fa8068203)

### Categorical data analysis
```py
df.nunique()
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/91bfd88e-0e49-49d8-b0c5-71b9ac16b0e0)

```py
df["Survived"].value_counts()
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/cdcf275d-042a-4754-935b-8ab5966ed3e9)

```py
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/de7753a5-37c9-496a-8b06-892d245abd6f)

```py
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/06747091-c02c-4a3b-af01-0d1c175ac42d)

```py
df
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/b6bbe089-8bf5-4272-b450-0e7f089fda8a)

```py
df.Pclass.unique()
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/74d1f411-bc4c-47ff-a560-74f270b49942)

```py
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/77618f16-976c-4fe9-8c00-aec73968276b)

### Bivariate Analysis
```py
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/999ac0a5-bea4-4e5b-a362-f2ccbfd28cc1)

```py
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/a24cf8be-1da3-4599-bc1f-ed345c7e43b6)

```py
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/416de460-1b9b-4082-a6ef-2d18e0f0ff2a)

```py
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/17d6abaa-1851-4992-ae5a-54f006e5d440)

```py
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/01a1a537-ae64-43bb-9f21-44d8b32879ce)

### Multivariate Analysis
```py
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/4a9d77aa-b747-4ce3-9b9e-4eeb40728806)

```py
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/f45d6e5c-799f-4eba-add9-b1837dce98b7)

# Co-relation
```py
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/6ad0bc8d-58a7-4093-8ba3-60b4cc8b2a3c)

```py
sns.pairplot(df)
```
![image](https://github.com/PriyankaAnnadurai/EXNO2DS/assets/118351569/43a838dc-8765-4c1b-9f81-c1d53d853265)

## RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
