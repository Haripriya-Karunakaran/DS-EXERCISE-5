# DS-EXERCISE-5
# FEATURE GENERATION
## AIM:
To read the given data and perform Feature Generation process and save the data to a file

## EXPLANATION:
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

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

# RESULT: 

Thus, the program to perform Feature Generation process on the given data set is successfully executed.


