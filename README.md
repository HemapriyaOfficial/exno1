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
# Result
          <<include your Result here>>
