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

NAME : NITHEESH YEGAVINTI 

REGISTER NO : 212224040370

```py
import pandas as pd  
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
<img width="900" height="727" alt="image" src="https://github.com/user-attachments/assets/ae9cc560-4e3b-422c-8894-50d2dcfba38a" />

```c
df.head
```
<img width="871" height="223" alt="image" src="https://github.com/user-attachments/assets/d8aba2d3-0b51-43d7-b4ca-6f9b1019b3db" />

```c
df.tail()
```
<img width="882" height="230" alt="image" src="https://github.com/user-attachments/assets/fc0a4791-9fda-41c7-8199-22cffa10a41a" />

```p
df.info()
```
<img width="406" height="412" alt="image" src="https://github.com/user-attachments/assets/e7fbbcf1-68e6-4505-b5ba-dc3199ee611c" />

```p
df.describe()
```
<img width="800" height="318" alt="image" src="https://github.com/user-attachments/assets/3b0fb304-053f-4462-9b85-a7c4987ea76f" />

```c
df.isnull().sum()
```
<img width="159" height="287" alt="image" src="https://github.com/user-attachments/assets/5c6a0186-7525-46d7-8104-ba37d5bc0b73" />

```c
df.isnull().any()
```
<img width="170" height="297" alt="image" src="https://github.com/user-attachments/assets/1d442f61-bce1-4032-a364-47467cca8f6e" />

```p
df.dropna()
```
<img width="893" height="457" alt="image" src="https://github.com/user-attachments/assets/d23c102a-9d47-47b1-9751-bcf4ca34fee2" />

```p
df.fillna(0)
```
<img width="903" height="710" alt="image" src="https://github.com/user-attachments/assets/c68a8383-43c1-4bd9-8483-d3a99af005b6" />

```p
df.fillna(method='ffill')
```
<img width="897" height="715" alt="image" src="https://github.com/user-attachments/assets/2417901a-afbe-4bd2-bb48-0b994369a214" />

```p
df.fillna({'GENDER':'MALE','Name':'SRI'})
```
<img width="892" height="712" alt="image" src="https://github.com/user-attachments/assets/1afbb415-f529-45ef-97e6-941ba75303c1" />


```p
ir=pd.read_csv("iris.csv")
ir
```
<img width="543" height="430" alt="image" src="https://github.com/user-attachments/assets/917b1852-c5e6-4871-a768-b3d7a5af0fef" />

```p
ir.describe()
```
<img width="489" height="298" alt="image" src="https://github.com/user-attachments/assets/14e2ee2f-94eb-4c97-a098-eb00208ef158" />

```p
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
<img width="672" height="579" alt="image" src="https://github.com/user-attachments/assets/50e66a5a-ec79-4bd9-bd30-590a413dce12" />

```p
Q1=ir.sepal_width.quantile(0.25)
Q3=ir.sepal_width.quantile(0.75)
(IQR)=Q3-Q1
print(IQR)
```
<img width="169" height="30" alt="image" src="https://github.com/user-attachments/assets/1dd9f77b-638b-401e-bf34-593e1185999a" />

```p
ran=ir[((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
ran['sepal_width']
```
<img width="351" height="121" alt="image" src="https://github.com/user-attachments/assets/c5b42aeb-7510-4ad9-a509-51e911153972" />


```p
ran=ir[~((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
ran['sepal_width']
```
<img width="499" height="264" alt="image" src="https://github.com/user-attachments/assets/75e16d4f-5071-4534-9cb7-65afc9a1beb4" />

```p
sns.boxplot(x='sepal_width',data=ran)
```
<img width="696" height="593" alt="image" src="https://github.com/user-attachments/assets/8c43ae40-a116-497f-acc5-e64f113c4a8b" />

```p
import numpy as np
import scipy.stats as stats
```
```p
z=np.abs(stats.zscore(ir['petal_length']))
z
```
<img width="485" height="274" alt="image" src="https://github.com/user-attachments/assets/4ce81688-b722-4f25-aa59-596fbee985bc" />

```p
ir1=ir[z<3]
ir1
```
<img width="539" height="431" alt="image" src="https://github.com/user-attachments/assets/5bdc2c3d-c08d-426c-bc56-ee20929abc92" />




# Result

Thus the given data successfully performed data cleaning and saved the cleaned data to a file
