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

import pandas as pd

df=pd.read_csv("/content/SAMPLEIDS.csv")

df


![image](https://github.com/user-attachments/assets/b897a009-b523-4c01-9b9d-64609d5100b8)

df.shape

![image](https://github.com/user-attachments/assets/69a614c2-43c2-49f3-9c09-3030f472c4e7)

df.describe()

      QAqSZ![image](https://github.com/user-attachments/assets/8603ae8f-f96d-448c-8879-e9337f780cdb)
      

df.info()

![image](https://github.com/user-attachments/assets/98ab7564-a0f6-4e94-9060-483e0d249a63)

# Result
          <<include your Result here>>
