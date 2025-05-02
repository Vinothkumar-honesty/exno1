# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS (1).csv")
df
```
![1 1](https://github.com/user-attachments/assets/38dec14e-7564-4c77-abc1-e61871ee388f)
```
df.shape
```
![1 2](https://github.com/user-attachments/assets/02852831-ae04-4db1-9e8a-b0c2c4600988)

```
df.describe()
```
![1 3](https://github.com/user-attachments/assets/f0030a6c-e9a5-4e2f-a015-7fc46eb5a5a8)

```
df.info()
```
![1 4](https://github.com/user-attachments/assets/6d985900-a8c9-424f-9803-37aeef931dd6)

```
df.head(10)
```
![1 5](https://github.com/user-attachments/assets/3f22789f-f3a3-4709-b2c5-b46fe1a9dc6e)

```
df.tail(10)
```
![1 6](https://github.com/user-attachments/assets/50950b76-bdee-422a-ac60-1cabf92501f2)

```
df.isnull().sum()
```
![1 7](https://github.com/user-attachments/assets/00a3002e-60c9-4495-8466-3a9d2522cfa4)

```
import pandas as pd
df=pd.read_csv("/SAMPLEIDS (1).csv")
df.notnull().sum()
```
![1 8](https://github.com/user-attachments/assets/b77dd30b-15f6-4386-a571-30bb3e48b75e)

```
df.dropna(how="any").shape
```
![1 9](https://github.com/user-attachments/assets/e0038052-0361-45b5-997f-107507849c8a)

```
df.dropna(how="all")
```
![1 10](https://github.com/user-attachments/assets/a945c452-4088-4d76-ba57-7b72f053f4b0)

```
df.dropna(axis=0,how="any")
```
![1 11](https://github.com/user-attachments/assets/ad0f6738-b151-4852-a35a-6bafaab4572d)

```
mn=df.TOTAL.mean()
mn
```
![1 12](https://github.com/user-attachments/assets/99ef99ad-235c-4ca3-9c72-ab4df37fb4d8)

```
df.TOTAL.fillna(mn,inplace=True)
df
```
![1 13](https://github.com/user-attachments/assets/ba309466-6a44-49ba-9d26-13b58594deb8)

```
df.isnull().sum()
```
![1 14](https://github.com/user-attachments/assets/b4c70add-1ef5-4e75-841d-0b46f11e7ba6)

```
df.M1.fillna(method="ffill",inplace=True)
df
```
![1 15](https://github.com/user-attachments/assets/739afc76-f792-4487-ab7c-58d3d28638f6)

```
df.isnull().sum()
```
![1 16](https://github.com/user-attachments/assets/5752947d-cc12-43b4-94bb-677b38d3fda9)

```
df.M2.fillna(method="ffill",inplace=True)
df
```
![1 17](https://github.com/user-attachments/assets/c9378c13-4e6b-427d-97b7-b2744c414503)

```
df.isnull().sum()
```
![1 18](https://github.com/user-attachments/assets/35091b4e-0713-43c3-9d8f-812cc1b68b7e)

```
df.M3.fillna(method="ffill",inplace=True)
df
```
![1 19](https://github.com/user-attachments/assets/148e5c54-76f4-49d2-8844-661311576b36)

```
df.isnull().sum()
```
![1 20](https://github.com/user-attachments/assets/f555d9e3-abf0-42ce-a41d-ccedbb263e5e)


```
df.drop_duplicates(inplace=True)
df
```
![1 21](https://github.com/user-attachments/assets/e342bd4c-de9b-466e-bcdd-6f4b5b469aed)

```
import pandas as pd
df=pd.read_csv("/SAMPLEIDS (1).csv")
mn=df.M1.mean()
df.M1.fillna(mn)
```
![1 22](https://github.com/user-attachments/assets/f3c613d5-a54e-4b8d-888d-af752066f232)

```
df.duplicated()
```
![1 23](https://github.com/user-attachments/assets/a93fc5d3-9031-48c8-bd79-e86279f6a4d1)

```
df['DOB']
```
![1 24](https://github.com/user-attachments/assets/7eb69ee4-6e9a-4b24-8082-b5fb4da34a24)

```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![1 25](https://github.com/user-attachments/assets/9b832a62-5ca0-4fd3-aef8-73e6081c33ee)

```
df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=True,annot=True)
```
![1 26](https://github.com/user-attachments/assets/aa170f23-6b62-44e2-9495-634083b7721b)

```
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
df=pd.DataFrame(age)
df
```
![1 27](https://github.com/user-attachments/assets/a4d62cd0-925c-468c-91d8-bc7e0754bab8)


```
sns.boxplot(data=df)
```
![1 28](https://github.com/user-attachments/assets/9bc8b8be-94a2-4b2d-b608-2797de000742)

```
import pandas as pd
import numpy as np
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![1 29](https://github.com/user-attachments/assets/2b097166-4c24-41a2-b39a-115e0a9a8b13)

```
sns.boxplot(data=af)
```
![1 30](https://github.com/user-attachments/assets/1eb71f4a-04ea-496a-a784-d635be4a3bb7)

```
q1=df.quantile(0.25)
q2=df.quantile(0.5)
q3=df.quantile(0.75)
iqr=q3-q1
iqr
```
![1 31](https://github.com/user-attachments/assets/f4782c4c-2f00-488f-8400-7c089b2eb69d)

```
import numpy as np
q1=np.percentile(df,25)
q3=np.percentile(df,75)
IQR=q3-q1
IQR
```
![1 32](https://github.com/user-attachments/assets/0d4706a6-b556-4901-a77c-e99d4f36113d)

```
lower_bond=q1-(1.5*iqr)
upper_bond=q3+(1.5*iqr)
lower_bond
```
![1 33](https://github.com/user-attachments/assets/d5b96087-89b4-42c3-a283-dec7f6a0d62d)

```
upper_bond
```
![1 34](https://github.com/user-attachments/assets/f5109da7-ab15-4d01-8f5b-4da01451c78c)

```
print("Q1:",q1)
print("Q3:",q3)
print("IQR:",iqr)
print("Lower Bond:",lower_bond)
print("Upper Bond:",upper_bond)
print("Outliers:",outliers)
```
![1 35](https://github.com/user-attachments/assets/6bc0fab9-bb05-435b-9b7c-a16cafd96907)

```
df=df[((df>=lower_bond)&(df<= upper_bond))]
df
```
![1 36](https://github.com/user-attachments/assets/3a60d0d8-5deb-46b5-8658-7a0161d7b3b7)

```
df=df.dropna()
df
```
![1 37](https://github.com/user-attachments/assets/3c5a52fb-84d2-48d3-8766-56655cb55f7a)

```
sns.boxplot(data=df)
```
![1 38](https://github.com/user-attachments/assets/d62f1e02-1185-496d-ab17-9c65af053bf7)

```
sns.scatterplot(data=df)
```
![1 39](https://github.com/user-attachments/assets/51c57407-5a02-47be-a276-a33ba5d21db6)

```
af.dropna()
```
![1 40](https://github.com/user-attachments/assets/83dae1f9-0b46-49a1-b36c-0182b6b211cc)

```
data=[1,2,2,2,3,2,1,1,15,2,2,2,3,1,1,2]
mean=np.mean(data)
std=np.std(data)
print("Mean of the dataset is",mean)
print("STD. deviation is",std)
```
![1 41](https://github.com/user-attachments/assets/e8dd1a5b-0e20-4aa1-89b1-b591e4baeeaa)

```
threshold=3
outlier=[]
for i in data:
  z=(i-mean)/std
  if z>threshold:
    outlier.append(i)
print("Outliers are",outlier)

```
![1 42](https://github.com/user-attachments/assets/a558370c-2115-4822-aa17-155029e3f33a)

```
from scipy import stats
data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df
```
![1 43](https://github.com/user-attachments/assets/a9556a85-e5ed-4baf-9c07-7683afd9e9d7)

```
z=np.abs(stats.zscore(df))
print(df[z['weight']>3])
```
![1 44](https://github.com/user-attachments/assets/9a90e347-8b35-489e-b8fa-76d6ed05cf6c)



           
# Result
   Thus We have cleaned the data and removed the outliers by detection using IQR and Z-score
