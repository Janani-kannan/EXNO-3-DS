## EXNO-3-DS

# AIM:
To read the given data and perform Feature Encoding and Transformation process and save the data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Encoding for the feature in the data set.
STEP 4:Apply Feature Transformation for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE ENCODING:
1. Ordinal Encoding
An ordinal encoding involves mapping each unique label to an integer value. This type of encoding is really only appropriate if there is a known relationship between the categories. This relationship does exist for some of the variables in our dataset, and ideally, this should be harnessed when preparing the data.
2. Label Encoding
Label encoding is a simple and straight forward approach. This converts each value in a categorical column into a numerical value. Each value in a categorical column is called Label.
3. Binary Encoding
Binary encoding converts a category into binary digits. Each binary digit creates one feature column. If there are n unique categories, then binary encoding results in the only log(base 2)ⁿ features.
4. One Hot Encoding
We use this categorical data encoding technique when the features are nominal(do not have any order). In one hot encoding, for each level of a categorical feature, we create a new variable. Each category is mapped with a binary variable containing either 0 or 1. Here, 0 represents the absence, and 1 represents the presence of that category.

# Methods Used for Data Transformation:
  # 1. FUNCTION TRANSFORMATION
• Log Transformation
• Reciprocal Transformation
• Square Root Transformation
• Square Transformation
  # 2. POWER TRANSFORMATION
• Boxcox method
• Yeojohnson method

# CODING AND OUTPUT:

  ```
       import pandas as pd

       df=pd.read_csv("C:\\Users\\admin\\Downloads\\data.csv")
       df
 ```
      
  <img width="545" height="375" alt="image" src="https://github.com/user-attachments/assets/58ca5168-2045-4b12-98e6-4210223f0045" />
       
 ```
       from sklearn.preprocessing import OrdinalEncoder,LabelEncoder
```
```
       df1=df.copy()
       df1=df.copy()
       education=["High School","Diploma","Bachelors","Masters","PhD"]
       enc=OrdinalEncoder(categories=[education])
       enc.fit_transform(df1[['Ord_2']])
      df1['ordinalencoder']=enc.fit_transform(df1[['Ord_2']])
      df1
```

  <img width="667" height="373" alt="image" src="https://github.com/user-attachments/assets/a6f8970c-a105-4180-aa8a-2617816fb84d" />


```
      df2=df.copy()
      enc=LabelEncoder()
      df1['LabelEncoder']=enc.fit_transform(df1[['Ord_2']])
      df1
```
   <img width="771" height="382" alt="image" src="https://github.com/user-attachments/assets/3f9e56ab-564a-4aef-91d8-e4a3757d105f" />
   
```
from sklearn.preprocessing import OneHotEncoder
```
```
df3=df.copy()
enc=OneHotEncoder()
newdata=pd.DataFrame(enc.fit_transform(df3[['City']]))
df4=pd.concat([df3,newdata],axis=1)
df4
```

  <img width="581" height="387" alt="image" src="https://github.com/user-attachments/assets/ef93bbb1-6af0-4c46-a298-9ffc6d5b36d8" />


```
pd.get_dummies(df4,columns=['City'])
```

<img width="912" height="367" alt="image" src="https://github.com/user-attachments/assets/08b486c6-6090-4c88-9d64-f213b83cdb20" />


```
pip install --upgrade category_encoders
```
 <img width="1250" height="493" alt="image" src="https://github.com/user-attachments/assets/7114fab0-3942-4975-9d81-82808c3eaa8b" />

```
from category_encoders import BinaryEncoder
```
```
df5=df.copy()
enc=BinaryEncoder()
newdata=pd.DataFrame(enc.fit_transform(df5[['Ord_1']]))
df6=pd.concat([df5,newdata],axis=1)
df6
```
  <img width="732" height="385" alt="image" src="https://github.com/user-attachments/assets/a1c27709-766e-4a98-8e5e-ff1c69c58431" />

```
from category_encoders import TargetEncoder
```
```
df7=df.copy()
enc=TargetEncoder()
newdata=pd.DataFrame(enc.fit_transform(df7[['Ord_1']],df7['Target']))
df8=pd.concat([df7,newdata],axis=1)
df8
```
  <img width="637" height="382" alt="image" src="https://github.com/user-attachments/assets/5d2b9b1e-8720-464c-af5e-8d7238284723" />




# RESULT:

       
      Thus the given data, Feature Encoding, Transformation process and save the data to a file was performed successfully.



       
