# EXERCISE-5      FEATURE GENERATION

## AIM:

To read the given data and perform Feature Generation process and save the data to a file

## EXPLANATION:

Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that

better relate to the target.

## ALGORITHM:

STEP 1: Read the given Data.

STEP 2: Clean the Data Set using Data Cleaning Process

STEP 3: Apply Feature Generation techniques to all the feature of the data set

STEP 4: Save the data to the file.

# CODE:

## data.csv

import pandas as pd

import numpy as np

import seaborn as sbn

import matplotlib.pyplot as plt

df = pd.read_csv("/content/data.csv")

df.head(5)

df.info()

df.isnull().sum()

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['Ord_2'] = le.fit_transform(df['Ord_2'])

sbn.set(style ="darkgrid")

sbn.countplot(x ='Ord_2', data = df)

from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder()

enc = enc.fit_transform(df[['City']]).toarray()

encoded_colm = pd.DataFrame(enc)

df = pd.concat([df, encoded_colm], axis=1)

df = df.drop(['City'], axis=1)

df.head(10)

df = pd.get_dummies(df, prefix=['Ord_2'], columns=['Ord_2'])

df.head(10)

df = pd.get_dummies(df, prefix=['Ord_1'], columns=['Ord_1'])

df.head(10)

## Encoding Data.csv

import pandas as pd

import numpy as np

import seaborn as sbn

import matplotlib.pyplot as plt

df = pd.read_csv("/content/Encoding Data.csv")

df1 = df.copy()

df1.head(5)

df = pd.get_dummies(df, columns = ['bin_1','bin_2'])

df

from sklearn.preprocessing importLabelEncoder,OrdinalEncoder,OneHotEncoder

climate = ['Cold','Warm','Hot']

enc = OrdinalEncoder(categories = [climate])

enc.fit_transform(df1[["ord_2"]])

df1['Ord_2'] = enc.fit_transform(df1[["ord_2"]])

df1.head(5)

df2 = df1.copy()

le = LabelEncoder()

df2['Nom_0'] = le.fit_transform(df2[["nom_0"]])

df2.head(5)

df3 = df2.copy()

oe = OneHotEncoder()

oe.fit_transform(df3[["bin_1"]])

df3.head(5)

df4 = df3.copy()

oe = OneHotEncoder()

oe.fit_transform(df4[["bin_2"]])

df4.head(5)

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['ord_2'] = le.fit_transform(df['ord_2'])

sbn.set(style ="darkgrid")

sbn.countplot(x ='ord_2', data = df)

## titanic_dataset.csv

import pandas as pd

import numpy as np

import seaborn as sbn

df = pd.read_csv("/content/titanic_dataset.csv")

df.head(5)

df.info()

df.isnull().sum()

df['Age']=df['Age'] . fillna(df['Age'].mean())

df['Cabin']=df['Cabin']. fillna(df['Cabin']. mode() [0])

df['Embarked']=df['Embarked'] . fillna(df['Embarked'].mode( )[0])

df.isnull().sum()

from sklearn.preprocessing import LabelEncoder

lc = LabelEncoder()

df['Sex'] = lc.fit_transform(df['Sex'])

sbn.set(style ="darkgrid")

sbn.countplot(x ='Sex', data = df)

from sklearn.preprocessing import OneHotEncoder

enc= OneHotEncoder()

enc= enc.fit_transform(df[['Name']]).toarray()

encoded_colm = pd.DataFrame(enc)

df= pd.concat([df, encoded_colm], axis=1)

df= df.drop(['Name'], axis=1)

df.head(10)

df = pd.get_dummies(df, prefix=['Ticket'] ,columns=['Ticket'])

df.head(10)

df = pd.get_dummies(df, prefix=['Embarked'] ,columns=['Embarked'])

df.head(10)

## OUTPUT:

![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/a878bd86-8b34-4451-95c5-22290ce76aa9)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/5d6ed4a9-714f-4e88-8528-953e81239892)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/aff5b389-0522-4e3f-9541-77560d7e8007)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/8e83338a-817b-4884-9cfe-7c0ae2e2e3f0)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/6d0f8049-6338-4714-bd99-4c7ba6711800)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/5fde3405-88b6-473c-8bd3-ef4fa4801401)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/efd1342a-c68d-49cb-aa8e-ab0d63141b77)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/519b4502-7aa1-48e3-b5e4-e25c36824b88)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/d4a60ce0-8ddd-487b-9220-b3e25598be5d)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/e2539cd2-9627-429b-b2d2-1edf17f07af6)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/2773d012-4083-4be5-8524-e69b2feddbbb)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/d4c32b35-e1d7-4677-91b8-9a206190149f)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/82d4424f-d563-400c-ae9a-1c8cd1349291)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/8c44942b-7be7-4e20-ac36-2d2b65ad1886)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/3122fd39-52fe-4bf7-a934-4c268cf528f7)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/3b055138-8aef-4e7e-a149-2408e32d0861)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/2f4559e3-1517-4e08-9380-d479e8b4e238)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/b73d3460-f9db-4bf8-8fd5-c0fb453b7982)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/be6dc079-9123-49f1-8b38-6217cb046a5c)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/118971e8-e304-42fd-bb9e-2c62178db031)
![image](https://github.com/Haripriya-Karunakaran/DS-EXERCISE-5/assets/126390051/c4693b50-8717-49a3-8cc4-055896208d50)

# RESULT: 

Thus, the program to perform Feature Generation process on the given data set is successfully executed.


