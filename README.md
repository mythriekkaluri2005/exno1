## NAME:E.MYTHRI
## REGISTRATION NUMBER:212223240034

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
![image](https://github.com/user-attachments/assets/582d5688-ebf0-435f-94de-9585626b06ff)

```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/5e4d622f-6988-4622-8c4d-f912257d9859)
```
df.isnull().any()
```
![image](https://github.com/user-attachments/assets/6b967149-7c54-4294-b3ba-e9f8bf380c56)

```
df.dropna()
```
![image](https://github.com/user-attachments/assets/9b50c0c2-958c-40d3-bd9b-40216d44f4d7)
```
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/b37346ba-6321-4cdb-b56f-c4b3eb46268b)

```
df.fillna(method = 'ffill')
```
![image](https://github.com/user-attachments/assets/d1955b12-bd6d-40ad-a5a9-7b8d8e251b1f)
```
df.fillna(method = 'bfill')
```
![image](https://github.com/user-attachments/assets/93f65a3a-9c65-4496-9c10-0fe46aa54650)
```
df_dropped = df.dropna()
df_dropped
```
![image](https://github.com/user-attachments/assets/385d2c2a-a03e-4324-809f-b267da0a8aed)

```
df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
![image](https://github.com/user-attachments/assets/8e7ac6ed-bb03-4a5c-aab1-4b08bebd3cf0)

```
import pandas as pd
ir=pd.read_csv('/content/iris.csv')
ir
```
![image](https://github.com/user-attachments/assets/cb0f7f06-8d0a-4499-874c-559e652f960c)

```
ir.describe()
```
![image](https://github.com/user-attachments/assets/74b1e559-c952-4e77-b6f5-a6eda164efb8)
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
![image](https://github.com/user-attachments/assets/8920ad5b-f165-4996-a47d-9dc9bde835f6)
```
 c1=ir.sepal_width.quantile(0.25)
 c3=ir.sepal_width.quantile(0.75)
 iq=c3-c1
 print(iq)
```
![image](https://github.com/user-attachments/assets/9d949f11-9802-4797-be0c-c39f0674ce6b)

```
 rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
 rid['sepal_width']
```
![image](https://github.com/user-attachments/assets/3622a7aa-4777-4b0c-b4a3-b58d1d26af41)
```
 delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
 delid
```
![image](https://github.com/user-attachments/assets/5cfc2a9b-4443-4abd-b333-41d42b711b31)
![image](https://github.com/user-attachments/assets/082ae5ed-ba4f-41cd-8069-46d4e1ed73c1)
```
 sns.boxplot(x='sepal_width',data=delid)
```
![image](https://github.com/user-attachments/assets/26fe0429-e809-4538-814e-31bf480bd519)

```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats

dataset=pd.read_csv('/content/heights.csv')
dataset
```
![image](https://github.com/user-attachments/assets/27fdda0e-6474-48ca-9dd0-94697d0104f2)

```
z = np.abs(stats.zscore(dataset['height']))
z
```
![image](https://github.com/user-attachments/assets/44acc566-c114-48f5-a5dd-5cabc4a1fdfc)
```
 df1 = df[z<3]
 df1
```
![image](https://github.com/user-attachments/assets/d4352ba4-27ed-433e-bab0-e97b26b1a23e)


# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
         
