# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

dt=pd.read_csv("titanic_dataset.csv")
dt
output<img width="1336" height="444" alt="image" src="https://github.com/user-attachments/assets/cf3946e2-0ee1-4f19-b4de-5b9a896b055c" />

dt.info()
output<img width="653" height="413" alt="image" src="https://github.com/user-attachments/assets/22273bdf-335f-4906-abe2-1c89ae4b3c7e" />

dt.shape
output<img width="899" height="43" alt="image" src="https://github.com/user-attachments/assets/2281a06d-5908-4b1c-b3b9-20572fafcd48" />

dt.describe()
output<img width="1055" height="320" alt="image" src="https://github.com/user-attachments/assets/d984524c-edf1-4893-88cf-b55e46ebcaba" />

dt.nunique()
output<img width="620" height="306" alt="image" src="https://github.com/user-attachments/assets/c6354b27-c3c8-43b3-8ea2-eeacd4156288" />

dt["Survived"].value_counts()
output<img width="621" height="74" alt="image" src="https://github.com/user-attachments/assets/b0952316-bc4f-4485-b662-7bec2bb10893" />

per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
output<img width="671" height="81" alt="image" src="https://github.com/user-attachments/assets/acabe319-c2e0-4adf-bce5-c595fa3464ea" />

sns.countplot(data=dt,x="Survived")
output<img width="1023" height="592" alt="image" src="https://github.com/user-attachments/assets/bd7833e0-e3e0-43b4-8967-3a5846589070" />

dt
output<img width="1340" height="457" alt="image" src="https://github.com/user-attachments/assets/4bb9e4f4-3e20-453d-8fd2-5cc0bf5d643f" />

dt.Pclass.unique()
output<img width="671" height="32" alt="image" src="https://github.com/user-attachments/assets/ff6d9092-e6f5-4fbf-bf1f-a42a055448ca" />

dt.rename(columns={'Sex':'Gender'},inplace=True)

sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
output<img width="1212" height="663" alt="image" src="https://github.com/user-attachments/assets/5e9699dd-0223-497a-809d-fc04f83aae15" />

sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
output<img width="1047" height="677" alt="image" src="https://github.com/user-attachments/assets/ef98837f-e8a3-4e01-83c1-3b0962f87912" />

dt.boxplot(column="Age",by="Survived")
output<img width="1010" height="628" alt="image" src="https://github.com/user-attachments/assets/b57deace-25fb-4f70-a329-3a6503548b21" />

sns.scatterplot(x=dt["Age"],y=dt["Fare"])
output<img width="1150" height="590" alt="image" src="https://github.com/user-attachments/assets/a8c9e72e-39f0-4349-818a-220a077f6a38" />

sns.jointplot(x="Age",y="Fare",data=dt)
output<img width="1065" height="770" alt="image" src="https://github.com/user-attachments/assets/4e509399-058f-4b42-ac53-c60650ec1ac5" />

fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
output<img width="1239" height="573" alt="image" src="https://github.com/user-attachments/assets/d187e91c-a0d5-4fde-98ad-9f001e21a1f2" />

sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
output<img width="1333" height="621" alt="image" src="https://github.com/user-attachments/assets/f4fb9337-95ad-4194-b972-a6bde93bdb79" />

corr=dt.corr()
sns.heatmap(corr,annot=True)
output<img width="1367" height="771" alt="image" src="https://github.com/user-attachments/assets/cc9f74c7-f0da-454d-b03e-5f7dfd10457b" />

sns.pairplot(dt)
output<img width="1377" height="728" alt="image" src="https://github.com/user-attachments/assets/13be25e0-7566-4bd5-a36d-8b08dbe415b4" />
      <img width="1351" height="555" alt="image" src="https://github.com/user-attachments/assets/d5a265d7-5b7a-4a1d-a45d-ff62c03e3f4c" />

# RESULT
        Thus the program to implement the data analysis has been successfully completed.
