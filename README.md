# Ex02-Outlier

You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR 

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

    (i) Using IQR detect weight outliers and print them

    (ii) Using IQR, detect height outliers and print them
    
# ALGORITHM:
# STEP 1
Read the given Data.

# STEP 2
Get the information about the data.

# STEP 3
Detect the Outliers using IQR method and Z score.

# STEP 4
Remove the outliers.

# STEP 5
Plot the datas using Box Plot.


# PROGRAM:
```
DEVELOPED BY: YUVABHARATHI.B, REGISTER NUMBER: 212222230181
import pandas as pd
df=pd.read_csv("/content/bhp.csv")
df.head()
df.describe()
df.info()
df.shape

import seaborn as sns
sns.boxplot(x="price_per_sqft",data=df)

### removing ouliers of bhp.csv file using IQR
Q1=df['price_per_sqft'].quantile(0.25)
Q3=df['price_per_sqft'].quantile(0.75)
IQR=Q3-Q1
lower=Q1-1.5*IQR
upper=Q3+1.5*IQR
newdata=df[(df['price_per_sqft']>=lower) & (df['price_per_sqft']<=upper)] 
print(newdata)   #new dataframe.
outliers=df[(df['price_per_sqft']<lower) | (df['price_per_sqft']>upper)]
print(outliers)
newdata.shape
sns.boxplot(x="price_per_sqft",data=newdata)


### removing ouliers of bhp.csv file using Zscore of 3

from scipy import stats
import numpy as np
z_score=np.abs(stats.zscore(df['price_per_sqft']))
newdata2=df[(z_score<3)]
print(newdata2)
outlier2=df[(z_score>=3)]
print(outlier2)
newdata2.shape
sns.boxplot(x="price_per_sqft",data=newdata2)

import pandas as pd
dataset=pd.read_csv("/content/height_weight.csv")
dataset.shape
dataset.describe()
dataset.info()
import seaborn as sns
sns.boxplot(x='height',data=dataset)

### Using IQR detect height outliers and print them( height_weight.csv)

Q1_height=dataset['height'].quantile(0.25)
Q3_height=dataset['height'].quantile(0.75)
IQR_HEIGHT=Q3_height-Q1_height
l_height=Q1_height-1.5*IQR_HEIGHT
u_height=Q3_height+1.5*IQR_HEIGHT
outliers_height=dataset[(dataset['height']<l_height) | (dataset['height']>u_height)]
print(outliers_height)
newdata_height=dataset[(dataset['height']>=l_height) & (dataset['height']<=u_height)]
print(newdata_height)
sns.boxplot(x='height',data=newdata_height)


### Using IQR, detect weight outliers and print them( height_weight.csv)

Q1_weight=dataset['weight'].quantile(0.25)
Q3_weight=dataset['weight'].quantile(0.75)
IQR_WEIGHT=Q3_weight-Q1_weight
l_weight=Q1_weight-1.5*IQR_WEIGHT
u_weight=Q3_weight+1.5*IQR_WEIGHT
outliers_weight=dataset[(dataset['weight']<l_weight) | (dataset['weight']>u_weight)]
print(outliers_weight)
newdata_weight=dataset[(dataset['weight']>=l_weight) & (dataset['weight']<=u_weight)]
print(newdata_weight)
sns.boxplot(x='weight',data=newdata_weight), REGISTER NUMBER: 212222230129
import pandas as pd
df=pd.read_csv("/content/bhp.csv")
df.head()
df.describe()
df.info()
df.shape

import seaborn as sns
sns.boxplot(x="price_per_sqft",data=df)

### removing ouliers of bhp.csv file using IQR
Q1=df['price_per_sqft'].quantile(0.25)
Q3=df['price_per_sqft'].quantile(0.75)
IQR=Q3-Q1
lower=Q1-1.5*IQR
upper=Q3+1.5*IQR
newdata=df[(df['price_per_sqft']>=lower) & (df['price_per_sqft']<=upper)] 
print(newdata)   #new dataframe.
outliers=df[(df['price_per_sqft']<lower) | (df['price_per_sqft']>upper)]
print(outliers)
newdata.shape
sns.boxplot(x="price_per_sqft",data=newdata)


### removing ouliers of bhp.csv file using Zscore of 3

from scipy import stats
import numpy as np
z_score=np.abs(stats.zscore(df['price_per_sqft']))
newdata2=df[(z_score<3)]
print(newdata2)
outlier2=df[(z_score>=3)]
print(outlier2)
newdata2.shape
sns.boxplot(x="price_per_sqft",data=newdata2)

import pandas as pd
dataset=pd.read_csv("/content/height_weight.csv")
dataset.shape
dataset.describe()
dataset.info()
import seaborn as sns
sns.boxplot(x='height',data=dataset)

### Using IQR detect height outliers and print them( height_weight.csv)

Q1_height=dataset['height'].quantile(0.25)
Q3_height=dataset['height'].quantile(0.75)
IQR_HEIGHT=Q3_height-Q1_height
l_height=Q1_height-1.5*IQR_HEIGHT
u_height=Q3_height+1.5*IQR_HEIGHT
outliers_height=dataset[(dataset['height']<l_height) | (dataset['height']>u_height)]
print(outliers_height)
newdata_height=dataset[(dataset['height']>=l_height) & (dataset['height']<=u_height)]
print(newdata_height)
sns.boxplot(x='height',data=newdata_height)


### Using IQR, detect weight outliers and print them( height_weight.csv)

Q1_weight=dataset['weight'].quantile(0.25)
Q3_weight=dataset['weight'].quantile(0.75)
IQR_WEIGHT=Q3_weight-Q1_weight
l_weight=Q1_weight-1.5*IQR_WEIGHT
u_weight=Q3_weight+1.5*IQR_WEIGHT
outliers_weight=dataset[(dataset['weight']<l_weight) | (dataset['weight']>u_weight)]
print(outliers_weight)
newdata_weight=dataset[(dataset['weight']>=l_weight) & (dataset['weight']<=u_weight)]
print(newdata_weight)
sns.boxplot(x='weight',data=newdata_weight)
```
# OUTPUT:

 bhp.csv IQR METHOD

# df.head()
![image](https://user-images.githubusercontent.com/113497404/227696838-6da81f11-3e41-4bd3-86ba-f9fc0baf9365.png)

# df.describe()
![image](https://user-images.githubusercontent.com/113497404/227697105-1f779ea1-24b0-4145-bda8-f568ae88dc21.png)

# df.info()
![image](https://user-images.githubusercontent.com/113497404/227697126-5efc0307-136c-4a86-b59b-040e9143be30.png)

# df.shape
![image](https://user-images.githubusercontent.com/113497404/227697171-41a9fc9b-4fe1-48c7-844f-12d8f44ed0a1.png)

# BOXPLOT BEFORE REMOVING OUTLIERS
![image](https://user-images.githubusercontent.com/113497404/227697213-80e86927-f189-45df-91df-5c5a6887e185.png)

# NEWDATA USING IQR
![image](https://user-images.githubusercontent.com/113497404/227697241-ad333083-05e4-483c-a1e4-c70e660b0166.png)

# OUTLIERS
![image](https://user-images.githubusercontent.com/113497404/227697476-fbddafa1-2130-4e80-82dc-273154567658.png)

# newdata.shape
![image](https://user-images.githubusercontent.com/113497404/227697518-785f0d51-f98a-46d8-8f4b-f64a1bae4160.png)

# BOXPLOT AFTER REMOVING OUTLIERS USING IQR
![image](https://user-images.githubusercontent.com/113497404/227697581-f4446720-7132-45c6-a7e4-badc738930b4.png)

# Zscore of 3
# NEWDATA USING Zscore
![image](https://user-images.githubusercontent.com/113497404/227697673-a00df278-d035-4ba7-bf42-da33ff21a503.png)

# OUTLIERS
![image](https://user-images.githubusercontent.com/113497404/227697693-bae715b2-f420-43e5-91a7-d9090285873d.png)

# newdata2.shape
![image](https://user-images.githubusercontent.com/113497404/227697767-6e93fce3-3e50-4ef7-a86c-caf7fdbc5d90.png)

# BOXPLOT AFTER REMOVING OUTLIERS USING Zscore
![image](https://user-images.githubusercontent.com/113497404/227697789-83f045c5-156b-4d76-94e4-3fb800735865.png)

# height_weight.csv
dataset.shape![image](https://user-images.githubusercontent.com/113497404/227697857-f2c11a94-df78-4b3f-a873-b27b4da14826.png)

# dataset.describe()
![image](https://user-images.githubusercontent.com/113497404/227697882-730d251b-ae49-4ff0-b703-07eef8d184e6.png)

# dataset.info()
![image](https://user-images.githubusercontent.com/113497404/227698010-f9552ce9-604b-4587-8b51-6ecb4ff22aaf.png)

# BOXPLOT BEFORE REMOVING OUTLIERS
![image](https://user-images.githubusercontent.com/113497404/227698030-c9088cfa-7760-49a7-ab7d-5bf7c3bf528f.png)

# HEIGHT OUTLIERS
![image](https://user-images.githubusercontent.com/113497404/227698040-84b3b0cc-a4c1-4015-b366-10b042d32870.png)

# DATASET AFTER REMOVING HEIGHT OUTLIERS
![image](https://user-images.githubusercontent.com/113497404/227698233-5cda3f93-d5ae-4828-998c-14d42c0c2f36.png)

# BOXPLOT AFTER REMOVING HEIGHT OUTLIERS
![image](https://user-images.githubusercontent.com/113497404/227698276-2d339b6f-a9b3-4485-8f2a-31e3328f4a26.png)

# WEIGHT OUTLIERS
![image](https://user-images.githubusercontent.com/113497404/227698304-6a7d6b8b-5fa1-4aa5-a73f-a5d190ab6f2f.png)

# DATASET AFTER REMOVING WEIGHT OUTLIERS
![image](https://user-images.githubusercontent.com/113497404/227698354-4327213f-ddb1-4eee-8e50-cc559b802e61.png)

# BOXPLOT AFTER REMOVING WEIGHT OUTLIERS
![image](https://user-images.githubusercontent.com/113497404/227698394-3b94d332-1a0a-4725-93b5-9001f2e70d0b.png)

# RESULT
The given datasets are read and outliers are detected and are removed using IQR and z-score methods.















