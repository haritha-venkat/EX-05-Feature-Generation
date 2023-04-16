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


# CODE:
```python
/* 
Name : HARITHASHREE.V
Register Number : 212222230046
**Feature Generation - Encoding Data.csv**
import pandas as pd
import numpy as np
import seaborn as sbn
df = pd.read_csv("/content/Encoding Data.csv")
df1 = df.copy()
df1.head(5)
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
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
from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(df['bin_1'])
df3  = pd.concat([df,data],axis=1)
df3.head(5)
df4 = df3.copy()
from category_encoders import BinaryEncoder
be1 = BinaryEncoder()
newdata = be.fit_transform(df['bin_2'])
df4  = pd.concat([df,newdata],axis=1)
df4.head(5)
df['ord_2'] = le.fit_transform(df['ord_2'])
sbn.set(style ="darkgrid")
sbn.countplot(df['ord_2'])

**Feature Generation - data.csv**
import pandas as pd
import numpy as np
import seaborn as sbn
df = pd.read_csv("/content/data.csv")
df.head(5)
df.info()
df.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
df['Ord_2'] = le.fit_transform(df['Ord_2'])
sbn.set(style ="darkgrid")
sbn.countplot(df['Ord_2'])
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

**Feature Generation - titanic_dataset.csv**
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
sbn.countplot(df['Sex'])
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
*/
```

# OUPUT:
## Feature Generation - Encoding Data.csv
![image](https://user-images.githubusercontent.com/121285701/232274541-f1959e4d-77ff-4688-b03e-2dc854f10a20.png)
![image](https://user-images.githubusercontent.com/121285701/232274551-974bf68a-711a-43ce-bfd1-2209810677bd.png)
![image](https://user-images.githubusercontent.com/121285701/232274578-ff3bc565-3232-4928-ac34-5742b00c6fe1.png)
## Feature Generation - data.csv
![image](https://user-images.githubusercontent.com/121285701/232274819-a1cd4646-ebfd-4d42-8580-40dcad1c7293.png)
![image](https://user-images.githubusercontent.com/121285701/232274827-74eb4e4c-ab59-42e9-8d8b-7395805715c6.png)
![image](https://user-images.githubusercontent.com/121285701/232274837-224c75e4-41d6-4a4d-b885-b2b99111f50f.png)
![image](https://user-images.githubusercontent.com/121285701/232274848-8ba26a28-8b96-4c9f-9e0f-46f51b213d25.png)
## Feature Generation - titanic_dataset.csv
![image](https://user-images.githubusercontent.com/121285701/232274949-4565a818-0742-4160-923b-733eaf0de869.png)
![image](https://user-images.githubusercontent.com/121285701/232274993-19f177c1-611d-4758-91a8-528b774e74f8.png)
![image](https://user-images.githubusercontent.com/121285701/232275022-46a0d3cd-7d38-4adb-8513-eed4816a0d39.png)
![image](https://user-images.githubusercontent.com/121285701/232275031-dde07511-938c-4649-875c-412b844cb055.png)
## RESULT:
Thus the Feature Generation for the given datasets had been executed successfully
