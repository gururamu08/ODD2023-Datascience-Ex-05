# Ex:05 Feature Generation

## AIM
   To read the given data and perform  Feature Encoding & Scaling process and save the data to a file.

## Explanation

   Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

## ALGORITHM

### STEP 1:

   Read the given Data

### STEP 2:
   Clean the Data Set using Data Cleaning Process

### STEP 3:   
   Apply Feature Generation techniques to all the feature of the data set

### STEP 4:
   Save the data to the file

## CODE
```
DEVELOPED BY : GURUMOORTHI R
REG NO: 212222230042
```
```
import pandas as pd
df=pd.read_csv("/content/Encoding Data.csv")
df
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
pm=['Hot','Warm','Cold']
e1=OrdinalEncoder(categories=[pm])
e1.fit_transform(df[["ord_2"]])
df['bo2']=e1.fit_transform(df[["ord_2"]])
df
le=LabelEncoder()
dfc=df.copy()
dfc['ord_2']=le.fit_transform(dfc['ord_2'])
dfc
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
df2=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))
df2=pd.concat([df2,enc],axis=1)
df2
from category_encoders import BinaryEncoder
df=pd.read_csv("/content/data.csv")
df
be=BinaryEncoder()
nd=be.fit_transform(df['Ord_2'])
dfb=pd.concat([df,nd],axis=1)
dfb1=df.copy()
dfb
from category_encoders import TargetEncoder
te=TargetEncoder
cc=df.copy()
new=te.fit_transform(X=cc["City"],y=cc["Target"])
cc=pd.concat([cc,new],axis=1)
cc
import pandas as pd
from scipy import stats
import numpy as np
df=pd.read_csv("/content/bmi.csv")
df.head()
df.dropna()
max_vals=np.max(np.abs(df[['Height','Weight']]))
max_vals
min_vals=np.min(np.abs(df[['Height','Weight']]))
min_vals
df1=df.copy()
df1
from sklearn.preprocessing import StandardScaler
sc=StandardScaler()
df1[['Height','Weight']]=sc.fit_transform(df1[['Height','Weight']])
df1.head(10)
max_vals=np.max(np.abs(df1[['Height','Weight']]))
max_vals
min_vals=np.min(np.abs(df1[['Height','Weight']]))
min_vals
df2=df.copy()
from sklearn.preprocessing import MinMaxScaler
scaler=MinMaxScaler()
df2[['Height','Weight']]=scaler.fit_transform(df[['Height','Weight']])
df2.head(10)
max_vals=np.max(np.abs(df2[['Height','Weight']]))
max_vals
min_vals=np.min(np.abs(df2[['Height','Weight']]))
min_vals
df2
df3=df.copy()
from sklearn.preprocessing import Normalizer
scaler=Normalizer()
df3[['Height','Weight']]=scaler.fit_transform(df3[['Height','Weight']])
df3
df4=df.copy()
from sklearn.preprocessing import MaxAbsScaler
scaler=MaxAbsScaler()
df4[['Height','Weight']]=scaler.fit_transform(df4[['Height','Weight']])
df4
df5=df.copy()
from sklearn.preprocessing import RobustScaler
scaler=RobustScaler()
df5[['Height','Weight']]=scaler.fit_transform(df5[['Height','Weight']])
df5.head()
```
## OUTPUT


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/90171cc3-62c5-4716-85be-bcc705dc4ea7)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/3ffe0405-411e-40b2-a43b-cf417c3d8906)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/6be3733d-5451-41e9-9722-0fd07e42aa9e)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/331c9204-4ef8-41e6-a6f4-78a875830b3b)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/f8f7493a-be4c-491d-ab29-3af5e689e025)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/d73cc6dd-8cc8-4850-886d-9e0fbe6f25c8)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/8954ac74-2238-4349-97e2-25fdffe73a2f)



![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/993bba4d-56d2-4969-ae3b-31ad2f8cd82c)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/5ca707ea-2929-4ca9-a4bf-c6a180be9488)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/6f37d8f3-6778-4492-9d92-927d935cfb8d)



![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/e94688ad-d131-441b-aead-31a1920a37bc)



![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/52c58ef5-2feb-45ba-a74e-f5880bee26e6)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/5381718a-5c34-49f4-a69b-2c71dc07babd)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/0e4e5183-d9f9-4668-8cb9-18a9d0b3e17a)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/b5123f0f-a22f-4e34-a246-954512af3360)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/f3ef4c78-8e3c-40c5-950c-3de00ec69221)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/ed65db9e-4b1a-4487-acd5-33860815e8c5)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/be2dc495-e14b-46d2-8001-d8e02b314770)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/0ba40019-1a93-46c3-98a7-f4f63eb94151)


![image](https://github.com/gururamu08/ODD2023-Datascience-Ex-05/assets/118707009/81261b97-9ee8-49fe-a0c3-626b45b38678)

## RESULT 

Thus the Feature Encoding and Scaling Process is Executed Successfully.













   
