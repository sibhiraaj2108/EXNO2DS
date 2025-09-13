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

## CODING
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
## OUTPUT
<img width="1196" height="440" alt="image" src="https://github.com/user-attachments/assets/ba517a0b-1caf-4311-a978-754720745d0f" />

## CODING
```
df.info()
```

## OUTPUT
<img width="390" height="334" alt="image" src="https://github.com/user-attachments/assets/87ca8d1d-a19f-4e9f-a0d9-595d373cf19e" />

## CODING
```
df.dtypes
```
## OUTPUT
<img width="259" height="431" alt="image" src="https://github.com/user-attachments/assets/e6fddc65-5cf1-4660-9d20-7d7a7e11f4a9" />

## CODING
```
df.value_counts()
```
## OUTPUT
<img width="1216" height="455" alt="image" src="https://github.com/user-attachments/assets/bd9e2064-8d94-41a1-a52f-60699c1ba833" />

## CODING
```
df['Age'].value_counts()
```
## OUTPUT
<img width="230" height="457" alt="image" src="https://github.com/user-attachments/assets/8cedea36-fc33-4e27-8e9a-c59b451b4ef7" />

## CODING
```
df.shape
```
## OUTPUT
<img width="220" height="29" alt="image" src="https://github.com/user-attachments/assets/dc0745a0-4fef-461c-8712-15a24815e045" />

## CODING
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
## OUTPUT
<img width="705" height="285" alt="image" src="https://github.com/user-attachments/assets/c8be6eb3-b300-47b8-89f4-cebc62a7a40f" />

## CODING
```
df.nunique()
```
## OUTPUT
<img width="214" height="399" alt="image" src="https://github.com/user-attachments/assets/ff60e809-950b-4f78-a151-1b3d80379232" />

## CODING
```
sns.countplot(data=df,x="Survived")
```
## OUTPUT
<img width="627" height="435" alt="image" src="https://github.com/user-attachments/assets/51ca11b9-3c91-4752-b383-739985f95209" />


## CODING
```
df.Pclass.unique()
```
## OUTPUT
<img width="233" height="37" alt="image" src="https://github.com/user-attachments/assets/0e0ccaf8-389b-435b-8603-297002c5e4a3" />

## CODING
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

## OUTPUT
<img width="1271" height="517" alt="image" src="https://github.com/user-attachments/assets/9378f668-f0e9-4a13-89e1-1e7df252f109" />

## CODING
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
## OUTPUT
<img width="1098" height="536" alt="image" src="https://github.com/user-attachments/assets/eed3b379-f7da-4773-9692-29b3a09f4232" />

## CODING
```
df.boxplot(column="Age",by="Survived")
```

## OUTPUT
<img width="830" height="509" alt="image" src="https://github.com/user-attachments/assets/8e95edbd-d38f-48fa-82bc-1fcce1025b8e" />

## CODING
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

## OUTPUT
<img width="774" height="476" alt="image" src="https://github.com/user-attachments/assets/016bf120-3564-47c8-b259-c634d19f9e8d" />

## CODING
```
fig, ax1 =plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
## OUTPUT
<img width="876" height="482" alt="image" src="https://github.com/user-attachments/assets/8a0512b8-f51e-43f2-b4eb-d11feb7262ff" />

## CODING
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
## OUTPUT
<img width="1390" height="536" alt="image" src="https://github.com/user-attachments/assets/bc6bbede-13f2-4fce-83a3-247035bbc0e4" />

## CODING
```
numeric_df = df.select_dtypes(include=np.number)
corr = numeric_df.corr()
sns.heatmap(corr, annot=True)
```

## OUTPUT
<img width="633" height="516" alt="image" src="https://github.com/user-attachments/assets/1ad7517c-e6e4-46db-a9f4-473763d2d49d" />

## RESULT
Thus the dataset value is found 
