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

```
import pandas as pd 
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns 
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![Screenshot 2024-08-29 102923](https://github.com/user-attachments/assets/1db6bf2e-81b2-4ee8-9e72-06a664c44e88)

```
df.info()
```
![Screenshot 2024-08-29 103005](https://github.com/user-attachments/assets/899d8035-6d22-4167-a3d1-d5506ab4efb2)

```
df.shape
```
![Screenshot 2024-08-29 103230](https://github.com/user-attachments/assets/90fb8983-77e5-4da8-bb94-3fc77add4913)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![Screenshot 2024-08-29 105006](https://github.com/user-attachments/assets/fcb9d1ba-6849-4205-a1a6-1db844bd1d7d)

```
df.nunique()
```
![Screenshot 2024-08-29 103313](https://github.com/user-attachments/assets/f7437042-9038-4549-88a3-adabed72993b)

```
df["Survived"].value_counts() 
```
![Screenshot 2024-08-29 103400](https://github.com/user-attachments/assets/1413fb78-0f0b-4fcf-b9e1-2b6ada814a89)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2) 
per
```
![Screenshot 2024-08-29 103735](https://github.com/user-attachments/assets/d7c5415e-8bca-4c37-aeb6-a2b6d28c87ae)

```
sns.countplot(data=df,x="Survived")
```
![Screenshot 2024-08-29 104019](https://github.com/user-attachments/assets/9ff211a4-f620-4676-a0e5-22c9f73d50a3)

```
df.Pclass.unique()
```
![Screenshot 2024-08-29 104223](https://github.com/user-attachments/assets/59565d88-18cd-44c7-9046-c492898f2be6)

```
df.rename(columns= {'Sex':'Gender'}, inplace=True)
df
```
![Screenshot 2024-08-29 104654](https://github.com/user-attachments/assets/56d55d69-7cb1-4493-8c1c-835d741e4237)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2024-08-29 105116](https://github.com/user-attachments/assets/ac4dc3e9-bf47-40a0-926f-6d091c3cc18d)

```
sns.catplot(x='Survived',hue="Gender",data=df,kind="count")
```
![Screenshot 2024-08-29 105148](https://github.com/user-attachments/assets/bac621e6-7003-4536-ab66-bcd171c89f07)

```
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2024-08-29 105216](https://github.com/user-attachments/assets/a2ad138a-57f9-4f88-bfb9-ebed45f3873b)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Screenshot 2024-08-29 105242](https://github.com/user-attachments/assets/c6ae5eb1-5df4-490b-b509-add76c135810)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2024-08-29 105311](https://github.com/user-attachments/assets/d2bd19cc-f6fa-40df-bf1d-a2a42acd8028)

```
fig,ax1 = plt.subplots(figsize=(8,5)) 
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![Screenshot 2024-08-29 105334](https://github.com/user-attachments/assets/cadad4f8-1ecf-4601-93a4-19652d13f521)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2024-08-29 105849](https://github.com/user-attachments/assets/e57d2f95-803b-4666-94db-1baba2607ab9)

```
sns.pairplot(df)
```
![Screenshot 2024-08-29 105555](https://github.com/user-attachments/assets/14e84556-7ef7-4a00-aed1-8317e70992a0)

DEVELOPED BY: KARTHIKEYAN S REG NO: 24900102
# RESULT
Hence, performing Exploratory Data Analysis on the given data set is successful.
