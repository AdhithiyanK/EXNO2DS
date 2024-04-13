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
![313611766-ad910c75-3f6b-455d-be51-ac5cc92b7482](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/9ea1500a-bfca-48d5-8026-9923dca981dc)
```
df.info()
```
![313611931-ffdc7bf5-442d-46d4-bb90-582ef03adf8b](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/54600144-67f1-4f9d-8b0f-1854b4a8782d)
```
df.shape
```
![313611964-67cef4ed-e81c-48f4-a2b7-9774461c2409](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/ef8f4e85-9193-443c-b232-53421dc6d3b5)
```
import pandas as pd
df=pd.read_csv("/content/titanic_dataset.csv")
df.set_index("PassengerId",inplace=True)
print(df.set_index)
```
![313612144-34f3bcbf-a69b-47a9-9cc7-3b8fc59df9f9](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/dfa260a6-7bcf-432d-80d6-cf8eb0ba92bb)
```
df.describe()
```
![313612161-8c940ad5-ebd1-4594-be50-1b8a4de34e36](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/afca2d50-83d4-4446-a8c7-012c39d19472)
```
df.nunique()
```
![313612183-f88906c6-9297-492f-9503-3f61d38ac697](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/8cfae12d-e5da-4a6d-970d-8e0bdfc10486)
```
df["Survived"].value_counts()
```
![313612226-00a55ce8-85c3-4cec-bd0f-be69931bdca1](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/7d02e421-cf2f-4c5e-96f0-bed29935b395)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![313612402-90af63f2-93ee-449b-bc9f-a1506e776d20](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/7cfc5ee6-8293-49b4-b070-8a3978a5a94d)

```
sns.countplot(data=df,x="Survived")
```
![313612414-823090a7-7559-45ff-a7e1-a41ecce49ae0](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/a0a3aee2-0da0-4cd2-9e4d-c616091263a1)
```
df
```
![313612427-9510f440-d240-4cb1-84c5-533ae425e724](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/cd0abd67-3780-4b29-8a82-732e915da795)

```
df.Pclass.unique()
```
![313612456-14faf5e5-c191-4eaa-8549-2699d83198c0](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/3e1be557-b69a-4248-95b5-87f6bf0e6595)
```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```
![313612731-52c3b934-6a43-4f63-9252-d7d0d9bb5e1d](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/a8576765-8d18-4ade-b2ce-b588540c0592)
```
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
![313612731-52c3b934-6a43-4f63-9252-d7d0d9bb5e1d](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/8fa6a561-8703-4765-899a-efcb6e013481)
```
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
![313612776-76d50ddb-0064-4867-af85-62136eb56edf](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/16cb7e19-a238-455d-aca2-e84383a515ac)
```
sns.catplot(x='Survived',hue='Sex',data=df,kind='count')
```
![313612797-3296021c-6de4-4ed8-9a04-4937be5ce50c](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/2307ede5-ff07-4d15-bedb-3a12333d903f)
```
df.boxplot(column='Age',by="Survived")
```
![313612824-e10fe226-cce7-4eaf-9b5f-dbac11d20928](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/3ca073a6-ed0c-4469-83b0-6728da88b78a)
```
sns.scatterplot(x=df['Age'],y=df["Fare"])
```
![313612852-98e64c92-8ff9-4276-8de1-6c53b369ab92](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/2fd03b50-b428-459a-9c4e-1d8e12856f7c)
```
import matplotlib.pyplot as plt
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
``
![313612877-154a4ef6-44c9-4451-8f71-c6c72957a48e](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/61074b03-cef3-4ad1-82c4-a262029e5b72)
```
sns.catplot(data=df,col='Survived',x='Sex',hue='Pclass',kind='count')
``
![313614352-34e25f68-d33b-441d-a781-73bf9fe64e80](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/4d244188-02e9-4c6d-8f18-01287c428b08)
```
import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![313614534-26c8e6cf-a84f-46ea-870f-f5e8a43924af](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/7424ee17-2cb4-45ef-9722-3bc7e6eccda7)
```
sns.pairplot(df)
```
![313615066-d8c0bcfb-1a6c-4dbd-a2a1-6bc00544c649](https://github.com/AdhithiyanK/EXNO2DS/assets/121029258/7b06916d-38bb-4200-a0a8-eed0e49b1175)

# RESULT
 Code are sucessfully executed.
