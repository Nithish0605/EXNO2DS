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
```import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
<img width="1302" height="556" alt="image" src="https://github.com/user-attachments/assets/0a68e686-5918-4687-9863-b0fd6f10f21f" />

```
df.info()
```
<img width="415" height="427" alt="image" src="https://github.com/user-attachments/assets/357e169d-17e5-4bab-8227-d72e4537c1c4" />

```
df.describe()
```
<img width="865" height="381" alt="image" src="https://github.com/user-attachments/assets/ebb900a5-8977-414e-862d-2de08b51f83e" />

```
df.dtypes
```
<img width="203" height="489" alt="image" src="https://github.com/user-attachments/assets/73c09db7-5e3d-404a-bfe5-2a0a8c57084b" />

```
df.shape
```
<img width="1347" height="613" alt="image" src="https://github.com/user-attachments/assets/d49a76c0-743d-435f-b9c8-4b70f9294f2f" />

```
df['Age'].value_counts()
```
<img width="213" height="490" alt="image" src="https://github.com/user-attachments/assets/4b0d8e5c-d237-44bb-93e7-b2f9d0e3b080" />

```
df.set_index("PassengerId", inplace=True)
df
```
<img width="1313" height="611" alt="image" src="https://github.com/user-attachments/assets/9c53fe72-ff91-4a02-a8be-50cb8103f942" />

```
df.nunique()
```
<img width="169" height="453" alt="image" src="https://github.com/user-attachments/assets/9889a4d8-81c0-4265-9584-fb71da975b55" />

```
sns.countplot(data=df,x='Age')
```
<img width="741" height="578" alt="image" src="https://github.com/user-attachments/assets/ba294556-c518-45b5-a860-bb9aa42331dc" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1300" height="592" alt="image" src="https://github.com/user-attachments/assets/24208181-7f86-42db-90f3-b53748c2052a" />

```
sns.catplot(x='Gender',col='Survived',kind='count',data=df,height=7,aspect=1)
```
<img width="1357" height="706" alt="image" src="https://github.com/user-attachments/assets/1d917f59-c916-47e1-abc0-457c45372ff6" />

```
df.boxplot(column='Age',by='Survived')
```
<img width="726" height="619" alt="image" src="https://github.com/user-attachments/assets/db611abf-e39f-4213-b237-d6a6d5dfa678" />

```
sns.scatterplot(x=df['Age'],y=df["Fare"])
```
<img width="735" height="587" alt="image" src="https://github.com/user-attachments/assets/38a72b9b-96e6-4d42-a956-97dbbdd6fdef" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="715" height="562" alt="image" src="https://github.com/user-attachments/assets/42ba0e3b-484b-4e52-9ed0-0298d411d907" />

```
sns.catplot(x='Pclass',y='Age',hue='Gender',col='Survived',kind='box',data=df)
```
<img width="1352" height="632" alt="image" src="https://github.com/user-attachments/assets/2f3ca9d6-9e0f-42b6-9fb5-9d656cac1889" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="755" height="643" alt="image" src="https://github.com/user-attachments/assets/c17cab6a-aeba-4425-9887-efd4b3be8b4e" />


# RESULT

Perform Exploratory Data Analysis on the given data set is successfull.
