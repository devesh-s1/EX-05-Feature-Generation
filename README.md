# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE

Developed by: DEVESH SHARMA S

Register no : 212222110008

Data:
```
import pandas as pd
df=pd.read_csv("data.csv")
print(df)
import category_encoders as ce
be=ce.BinaryEncoder()
df1=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
df1
be=ce.BinaryEncoder()
df2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
df2
df1=df.copy()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder,OneHotEncoder
import category_encoders as ce
be=ce.BinaryEncoder()
ohe=OneHotEncoder(sparse=False)
le=LabelEncoder()
oe=OrdinalEncoder()
df1["City"] = ohe.fit_transform(df1[["City"]])
temp=['Cold','Warm','Hot','Very Hot']
oe1=OrdinalEncoder(categories=[temp])
df1['Ord_1'] = oe1.fit_transform(df1[["Ord_1"]])
edu=['High School','Diploma','Bachelors','Masters','PhD']
oe2=OrdinalEncoder(categories=[edu])
df1['Ord_2']= oe2.fit_transform(df1[["Ord_2"]])
df1
## SCALING:
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=(['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target']))
df2
from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df3
from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df4
from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df5
```
Encoding data:
```
import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df
```
## GENERATION
```
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
ndf
be=ce.BinaryEncoder()
ndf2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
ndf2
df1=df.copy()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
le=LabelEncoder()
oe=OrdinalEncoder()
df1["nom_0"] = oe.fit_transform(df1[["nom_0"]])
temp=['Cold','Warm','Hot']
oe2=OrdinalEncoder(categories=[temp])
df1['ord_2'] = oe2.fit_transform(df1[['ord_2']])
df1
```
## SCALING:
```
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df0=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df0
from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df2=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df2
from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df3=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df3
from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df4=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df4
```
Titanic Dataset:
```
import pandas as pd
df=pd.read_csv("titanic_dataset.csv")
df
df.drop("Name",axis=1,inplace=True)
df.drop("Ticket",axis=1,inplace=True)
df.drop("Cabin",axis=1,inplace=True)
df.isnull().sum()

df["Age"]=df["Age"].fillna(df["Age"].median())
df["Embarked"]=df["Embarked"].fillna(df["Embarked"].mode()[0])
df.isnull().sum()
df
```
## ENCODING
```
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df['Sex'])
ndf
df1=df.copy()
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
embark=['S','C','Q']
e1=OrdinalEncoder(categories=[embark])
df1['Embarked'] = e1.fit_transform(df[['Embarked']])
df1

## SCALING
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df0=pd.DataFrame(sc.fit_transform(df1),columns=['PassengerId', 'Survived', 'Pclass', 'Sex','Age','SibSp','Parch','Fare','Embarked'])
df0
from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df2=pd.DataFrame(sc1.fit_transform(df1),columns=['PassengerId', 'Survived', 'Pclass', 'Sex','Age','SibSp','Parch','Fare','Embarked'])
df2
from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df3=pd.DataFrame(sc2.fit_transform(df1),columns=['PassengerId', 'Survived', 'Pclass', 'Sex','Age','SibSp','Parch','Fare','Embarked'])
df3
from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df4=pd.DataFrame(sc3.fit_transform(df1),columns=['PassengerId', 'Survived', 'Pclass', 'Sex','Age','SibSp','Parch','Fare','Embarked'])
df4
```

OUTPUT
(i) Data.csv

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/0d43c483-4d42-4c45-8c03-4984deb3d155)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/7768d8ec-a853-477e-b3a8-dfc65edd00eb)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/55af06ff-5481-40ca-b1e4-6b9b1c460a83)


![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/b7aad5e3-1079-40c2-bf06-7aba817c7a26)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/0452383c-0065-41f5-a1ce-244aed30b419)


![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/579ad487-d7a0-41c5-9dae-d02adeb10dcc)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/111afea8-3195-469c-b641-4b9f36c4a6bd)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/15cf98ef-0039-4e8d-a73e-583e19554178)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/411775da-9980-4ec7-908f-8bc1d406d8b0)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/b196bd1b-6fd6-43f2-82d5-3ec0cd7b1965)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/03e9d91f-cf65-4202-9e2c-3716e6b86b68)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/629674a2-f66f-4b6d-81e6-3ea5ef73526a)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/d86535a7-490c-47cd-9642-2c3527c3c912)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/9137bf70-7843-4bdf-b727-8d060774e732)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/e68c7c57-c126-476d-85d8-c1abe78e389e)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/c1872cc9-dcb7-4659-b0dd-8697b46cf750)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/2542211a-09d2-4248-b61e-b5f89ac5a611)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/c150526e-c2d4-41bb-b356-85ca3064876b)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/8a2da25f-94cb-4d7e-898e-348a92267912)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/8d0c03d2-46be-4834-a75b-82208df82523)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/d063d580-ff80-49f1-af10-11ca8b467d38)

![image](https://github.com/devesh-s1/EX-05-Feature-Generation/assets/121490523/72ee1a7e-b3b9-4ab6-a0c2-f2405dd6a4a9)

