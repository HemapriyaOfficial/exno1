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
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/user-attachments/assets/b897a009-b523-4c01-9b9d-64609d5100b8)

```
df.shape
```
![image](https://github.com/user-attachments/assets/69a614c2-43c2-49f3-9c09-3030f472c4e7)

```
df.describe()
```
![image](https://github.com/user-attachments/assets/17aad8ea-9ee8-4cdb-b807-9f2dea3fc5e3)

```
df.info()
```
![image](https://github.com/user-attachments/assets/98ab7564-a0f6-4e94-9060-483e0d249a63)
```
df.head(5)
```
![image](https://github.com/user-attachments/assets/6f6cae3c-ca17-4ae5-b4d3-5e18a0e2c9d6)
```
df.tail(5)
```
![image](https://github.com/user-attachments/assets/8fa955ca-75e9-46e6-aca6-93ba6acdc9af)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/650a621b-e7ee-492d-9ee7-f08a4e9251d7)
```
df.dropna(how='any').shape
```
![image](https://github.com/user-attachments/assets/c5798044-47c3-48d8-aa6d-d9a008999582)
```
mn=df.TOTAL.mean()
mn
```
![image](https://github.com/user-attachments/assets/e82d9c38-059f-48ab-bd5e-7876307f26fe)
```
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/user-attachments/assets/dd6f3849-0dcb-483e-8cfd-7aacc2172e9c)
```
df['M1']
```
![image](https://github.com/user-attachments/assets/4de60bdb-f2d9-40e0-b204-0ba1e28939dc)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/2c6397e9-fc19-4224-a2ad-2de07b24a749)

```
df['M1'].fillna('ffill',inplace=True)
df
```
![image](https://github.com/user-attachments/assets/d4c2b7ff-2a2a-47fb-8a74-c56c001b4866)
```
df.duplicated()
```
![image](https://github.com/user-attachments/assets/79781e27-b1d1-4385-b998-1e6372c15c25)
```
df.drop_duplicates(inplace=True)
df.duplicated()
```
![image](https://github.com/user-attachments/assets/2746da78-059f-4bc9-ae5f-93a19cf40e93)
```
df['DOB']
```
![image](https://github.com/user-attachments/assets/5233cd4f-f3c5-46b0-9fad-8b06d26afb2c)
```
import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/user-attachments/assets/40deaf35-a80b-4fac-b09b-5734cf7490ac)
```
df.dropna(inplace=True)
df
```
![image](https://github.com/user-attachments/assets/055814a3-bb00-4013-b5df-b083a2b93277)
```
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/user-attachments/assets/554c7fd9-7709-42ed-9311-88b4e451aef7)
```
import pandas as pd
import seaborn as sns
import numpy as np
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/user-attachments/assets/b6c13c25-8cee-4f63-b9d9-afca76312904)
```
sns.boxplot(data=af)
```
![image](https://github.com/user-attachments/assets/f028442f-2de8-4315-be71-7b5b140cc66a)
```
sns.scatterplot(data=af)
```
![image](https://github.com/user-attachments/assets/54774885-e57c-4537-a088-973a340d99be)
```
Q1=np.percentile(af,25)
Q3=np.percentile(af,75)
IQR=Q3-Q1
IQR
```
![image](https://github.com/user-attachments/assets/515bd50d-484b-4137-aa6a-d1ef91116391)

```
lower_bound=q1-1.5*iqr
upper_bound=q3+1.5*iqr
lower_bound
```
![image](https://github.com/user-attachments/assets/d98bcdb4-1310-4316-a6f4-28aa1b563ed1)
```
upper_bound
```
![image](https://github.com/user-attachments/assets/5437648b-c7b1-428d-b43c-46c2aee2b453)
```
outliers = [x for x in age if x < lower_bound.iloc[0] or x > upper_bound.iloc[0]]
print("Q1:",Q1)
print("Q3:",Q3)
print("IQR:",IQR)
print("Lower bound:",lower_bound)
print("Upper bound:",upper_bound)
print("Outliers:",outliers)
```
![image](https://github.com/user-attachments/assets/126e1236-0713-4903-8452-8d46a8db2179)
```
af=af[((af>=lower_bound)&(af<=upper_bound))]
af
```
![image](https://github.com/user-attachments/assets/31a6cb79-f05a-4f96-aeaf-3d739d53ff56)
```
af.dropna()
```
![image](https://github.com/user-attachments/assets/fc949cea-653a-4397-b283-36c30a84e9e0)
```
sns.boxplot(data=af)
```
![image](https://github.com/user-attachments/assets/be5b0b44-0e4d-44b5-b34f-dbbd65897a29)
```
sns.scatterplot(data=af)
```
![image](https://github.com/user-attachments/assets/825b257c-6ec2-4553-b2ac-5e1c2b8e186e)
```
data=[1,2,2,2,3,1,1,15,2,2,2,3,1,1,2]
mean=np.mean(data)
std=np.std(data)
print('mean of the dataset is',mean)
print('std.deviation is',std)
```
![image](https://github.com/user-attachments/assets/72e80852-a9bf-48a4-95e3-d6b7677a2264)
```
threshold=3
outlier=[]
for i in data:
  z=(i-mean)/std
  if z>threshold:
    outlier.append(i)
    print('outlier in dataset is',outlier)
```
![image](https://github.com/user-attachments/assets/aeb8219a-f21e-4737-b11b-ffe6367b5984)

# Result

Thus the given program was  executed successfully.
