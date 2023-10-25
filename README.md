# Ex:05 Feature Generation
# Aim:
To read the given data and perform Feature Generation process and save the data to a file.

# Explanation:
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

# Algorithm:
Step 1: Read the given Data.

Step 2: Clean the Data Set using Data Cleaning Process.

Step 3: Apply Feature Generation techniques to all the feature of the data set.

Step 4: Save the data to the file.

# PROGRAM:
Name: Manoj Kumar G   
Reg no: 212222230078

## Encoding Data:
### ENCODING DATA:
```
import pandas as pd
import numpy as np
from scipy import stats
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Encoding Data (1).csv")
df=pd.DataFrame(data)
df

from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
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
pd.get_dummies(df2,columns=["nom_0"])

pip install --upgrade category_encoders

from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(dfc['bin_1'])
dfc = pd.concat([dfc,data],axis=1)
dfc

be1 = BinaryEncoder()
data = be1.fit_transform(dfc['bin_2'])
dfc = pd.concat([dfc,data],axis=1)
dfc
```
### OUTPUT:
### Initial Data:
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/b471f515-48d1-4e09-90aa-d077bf7ace8a)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/a8c974ff-e759-4613-ba48-95ff81d01409)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/5362b265-38b2-4537-b5e8-7ee200853193)
### Label encoder:
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/fb98a6f1-3d70-4f88-9a67-abddaa7270bf)
### OneHotEncoder:
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/587e2c45-1780-4470-9d01-798b9945324b)
### BinaryEncoder:
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/e153df68-f451-4870-a4b2-6f92bbcad64b)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/0252c6c9-3e69-4cc7-9474-e80bb189cf7e)

## DATA
### CODE:
```
import pandas as pd
import numpy as np
from scipy import stats
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("/content/data.csv")
df=pd.DataFrame(data)
df

from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
pm=['Hot','Warm','Cold','Very Hot']
e1=OrdinalEncoder(categories=[pm])
e1.fit_transform(df[["Ord_1"]])
df['bo2']=e1.fit_transform(df[["Ord_1"]])
df

le=LabelEncoder()
dfc=df.copy()
dfc['Ord_1']=le.fit_transform(dfc['Ord_1'])
dfc

from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
df2=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df2[['City']]))
df2=pd.concat([df2,enc],axis=1)
pd.get_dummies(df2,columns=["City"])

pip install --upgrade category_encoders

from category_encoders import BinaryEncoder
be = BinaryEncoder()
data = be.fit_transform(dfc['bin_1'])
dfc = pd.concat([dfc,data],axis=1)
dfc

be1 = BinaryEncoder()
data = be1.fit_transform(dfc['bin_2'])
dfc = pd.concat([dfc,data],axis=1)
dfc
```
### OUTPUT:
### Initial Data:
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/eee325f8-55fa-4112-80c4-1803cc0a3ab5)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/408c91f2-319f-4006-9c5c-5977652fc0bc)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/8c6272d0-e006-4821-9add-bd790779614a)
### Label encoder:
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/914d4b57-770a-4619-88c2-4c3c9b746168)
### OneHotEncoder:
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/45aed00d-669e-4eba-9021-297edd03478f)
### BinaryEncoder:
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/1027e36e-9e36-4fee-a9d9-a05956a2734d)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-05/assets/119407186/96a9a687-0c38-47a8-8fdd-e86586a249f2)

# RESULT:
The above Feature Generation process has been Executed Seccessfully.
