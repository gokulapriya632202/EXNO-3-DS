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
       # INCLUDE YOUR CODING AND OUTPUT SCREENSHOTS HERE
```
import pandas as pd
df=pd.read_csv("/content/Encoding Data.csv")
df
```

![Screenshot 2024-03-26 161552](https://github.com/gokulapriya632202/EXNO-3-DS/assets/119560302/a637f1a6-5e6d-4fcb-8ede-285e2d41aafc)

```
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
pm=['Hot','Warm','Cold']
e1=OrdinalEncoder(categories=[pm])
e1.fit_transform(df[["ord_2"]])
```

![Screenshot 2024-03-26 161656](https://github.com/gokulapriya632202/EXNO-3-DS/assets/119560302/1eab3a81-cf03-401d-9e7c-1d21381946fa)

```
df['bo2']=e1.fit_transform(df[["ord_2"]])
df
```

![Screenshot 2024-03-26 161701](https://github.com/gokulapriya632202/EXNO-3-DS/assets/119560302/064e9035-a217-465c-bf0d-baeaf38a142f)

```
le=LabelEncoder()
dfc=df.copy()
dfc['ord_2']=le.fit_transform(dfc['ord_2'])
dfc
```
![Screenshot 2024-03-26 161707](https://github.com/gokulapriya632202/EXNO-3-DS/assets/119560302/cc581ce4-82e8-42a9-8d9c-37a1b365ffbc)

```
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
df2=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df2[["nom_0"]]))
```

![Screenshot 2024-03-26 161716](https://github.com/gokulapriya632202/EXNO-3-DS/assets/119560302/4d93974b-16f9-4b27-9d00-4cc0abee08d0)

```
df2=pd.concat([df2,enc],axis=1)
df2
```

![Screenshot 2024-03-26 161722](https://github.com/gokulapriya632202/EXNO-3-DS/assets/119560302/74c5c492-dd39-4f11-a75a-64f6a28707bc)

```
pd.get_dummies(df2,columns=["nom_0"])
```

![Screenshot 2024-03-26 161729](https://github.com/gokulapriya632202/EXNO-3-DS/assets/119560302/b39577a2-d937-4e22-8623-e19735380801)

```
pip install --upgrade category_encoders
```
![Screenshot 2024-03-26 162300](https://github.com/gokulapriya632202/EXNO-3-DS/assets/119560302/3066f410-80e3-4069-be2d-4b056d132b48)

```


# RESULT:
       # INCLUDE YOUR RESULT HERE

       
