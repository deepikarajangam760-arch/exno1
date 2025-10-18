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

data=pd.read_csv(r"C:\Users\DEEPIKA\Downloads\Data_set (1).csv")

print(data)

<img width="815" height="826" alt="image" src="https://github.com/user-attachments/assets/2bf9e129-ff06-48c6-8229-e72fb003d730" />
df.describe()

<img width="824" height="368" alt="image" src="https://github.com/user-attachments/assets/51363d84-43db-46e2-8bb4-e174fe99986d" />

df=pd.DataFrame(data)

print(df.isnull())

<img width="685" height="569" alt="image" src="https://github.com/user-attachments/assets/132cbd6c-0067-4eb8-b20a-b5fe9596aa8e" />

df=pd.DataFrame(data)

print(df.isnull().sum())

<img width="300" height="225" alt="image" src="https://github.com/user-attachments/assets/db5c5972-939c-4617-b5a3-c888471e881f" />

df.info()

<img width="404" height="272" alt="image" src="https://github.com/user-attachments/assets/247c22e9-71ee-4ef1-9267-3dc9d3c21974" />

import pandas as pd

data=pd.read_csv(r"C:\Users\DEEPIKA\Downloads\Data_set (1).csv")

df=pd.DataFrame(data)

dfd=df.dropna()

print("AFTER DROPNA")

print(dfd)

<img width="670" height="875" alt="image" src="https://github.com/user-attachments/assets/9e6e60cd-b4e1-4d5a-8e47-898a83743549" />

dfd=df.dropna(axis=1)

print("AFTER DROPNA")

print(dfd)

<img width="526" height="316" alt="image" src="https://github.com/user-attachments/assets/872a8cc6-04a0-4f27-9f6b-32fe204bd088" />
dfd=df.dropna(axis=1,inplace=True)

print("AFTER DROPNA")

print(dfd)

<img width="508" height="44" alt="image" src="https://github.com/user-attachments/assets/1c4d7a93-c304-433b-893d-9198004e02c3" />

df=pd.DataFrame(data)

df1=df.iloc[[1,3,5],[1,3]]

print(df1)

<img width="423" height="92" alt="image" src="https://github.com/user-attachments/assets/fe109e8a-0de5-494f-be28-c7d4ed902662" />

dfd=df.dropna(axis=0)

print("AFTER DROPNA")

print(dfd)

<img width="660" height="324" alt="image" src="https://github.com/user-attachments/assets/9ae2391e-be3e-49b6-959e-34c9296328a7" />

df=pd.DataFrame(data)

print(df.isnull().any())

<img width="343" height="213" alt="image" src="https://github.com/user-attachments/assets/1aeed245-2f0b-498c-a1bd-260ff0a4435e" />

dfd=df.fillna(0)

print("AFTER FILLNA")

print(dfd)

<img width="751" height="862" alt="image" src="https://github.com/user-attachments/assets/955755ee-f632-41ab-b88c-9b0282cbc253" />

dfd=df.fillna(method="ffill")

print("AFTER FILLNA")

print(dfd)

<img width="736" height="866" alt="image" src="https://github.com/user-attachments/assets/56369c7b-7f98-4424-98ad-e629548da0a1" />

dfd=df.fillna(method="bfill")

print("AFTER FILLNA")

print(dfd)

<img width="738" height="866" alt="image" src="https://github.com/user-attachments/assets/64248c9a-0b28-4c7d-a52e-06fdc32c28ad" />

dfd=df.fillna({'show_name':'nandy','aired_on':'wednesday','original_network':'Jio','rating':7.5})

print("AFTER FILLNA")

print(dfd)

<img width="794" height="876" alt="image" src="https://github.com/user-attachments/assets/883d3ab7-fb0f-4823-b642-1dec96a62f55" />

import pandas as pd

import matplotlib.pyplot as plt

import numpy as np

data=pd.read_csv("iris.csv")

df=pd.DataFrame(data)

print(df)

x=df["petal_length"]

y=df["sepal_length"]

plt.bar(x,y)

plt.show()

<img width="691" height="811" alt="image" src="https://github.com/user-attachments/assets/0830d281-86bd-4f1d-a83b-a083ebf2cd34" />

import pandas as pd

import matplotlib.pyplot as plt

import numpy as np

data=pd.read_csv("iris.csv")

df=pd.DataFrame(data)

print(df)

x=df["petal_length"]

y=df["sepal_length"]

plt.xlabel('X-axis')

plt.ylabel('Y-axis')

plt.plot(x,y)

plt.show()

<img width="754" height="831" alt="image" src="https://github.com/user-attachments/assets/8a7cf455-4a7d-482f-b347-aba042c54ef5" />

plt.scatter(x,y)

plt.show()

<img width="730" height="516" alt="image" src="https://github.com/user-attachments/assets/7adb35d8-bd50-4371-a5cf-f68c3c2d39d1" />

import pandas as pd

import matplotlib.pyplot as plt

import numpy as np

data=pd.read_csv("iris.csv")

df=pd.DataFrame(data)

print(df)

dff=plt.boxplot(x="petal_width",data=df)

print(dff)

<img width="1353" height="892" alt="image" src="https://github.com/user-attachments/assets/ab12d175-425c-4939-a6bc-a07863db974e" />

import pandas as pd

import numpy as np

from scipy import stats

data=pd.read_csv("iris.csv")

df=pd.DataFrame(data)

z_scores = np.abs(stats.zscore(df.select_dtypes(include=[np.number])))

df_cleaned = df[(z_scores < 3).all(axis=1)]

df_cleaned

<img width="569" height="513" alt="image" src="https://github.com/user-attachments/assets/15fb2645-951e-46dd-86ce-33738a60bcca" />

import pandas as pd

import numpy as np

data_set = pd.read_csv("iris.csv")

df = pd.DataFrame(data_set)

Q1 = df["sepal_width"].quantile(0.25)

Q3 = df["sepal_width"].quantile(0.75)

IQR = Q3 - Q1

lower_bound = Q1 - 1.5 * IQR

upper_bound = Q3 + 1.5 * IQR

print("The Orginal DataSet")

print(df)

outliers = df[(df['sepal_width'] < lower_bound) | (df['sepal_width'] > upper_bound)]

print("The Outliers")

print(outliers)

df_clean = df[(df['sepal_width'] >= lower_bound) & (df['sepal_width'] <= upper_bound)]

print("The Dataset after removing the outliers")

print(df_clean)

<img width="653" height="771" alt="image" src="https://github.com/user-attachments/assets/57017879-7e75-4eed-a7f5-0b87a541e219" />



      



















# Result
THUS DATA CLEANING IS PERFORMED
          
