<H3>NAME : Naveenaa A K</H3>
<H3>REGISTER NO: 212222230094</H3>
<H3>EX. NO.1</H3>
<H3>DATE</H3>
<H1 ALIGN =CENTER> Introduction to Kaggle and Data preprocessing</H1>

## AIM:

To perform Data preprocessing in a data set downloaded from Kaggle

## EQUIPMENTS REQUIRED:
Hardware – PCs
Anaconda – Python 3.7 Installation / Google Colab /Jupiter Notebook

## RELATED THEORETICAL CONCEPT:

**Kaggle :**
Kaggle, a subsidiary of Google LLC, is an online community of data scientists and machine learning practitioners. Kaggle allows users to find and publish data sets, explore and build models in a web-based data-science environment, work with other data scientists and machine learning engineers, and enter competitions to solve data science challenges.

**Data Preprocessing:**

Pre-processing refers to the transformations applied to our data before feeding it to the algorithm. Data Preprocessing is a technique that is used to convert the raw data into a clean data set. In other words, whenever the data is gathered from different sources it is collected in raw format which is not feasible for the analysis.
Data Preprocessing is the process of making data suitable for use while training a machine learning model. The dataset initially provided for training might not be in a ready-to-use state, for e.g. it might not be formatted properly, or may contain missing or null values.Solving all these problems using various methods is called Data Preprocessing, using a properly processed dataset while training will not only make life easier for you but also increase the efficiency and accuracy of your model.

**Need of Data Preprocessing :**

For achieving better results from the applied model in Machine Learning projects the format of the data has to be in a proper manner. Some specified Machine Learning model needs information in a specified format, for example, Random Forest algorithm does not support null values, therefore to execute random forest algorithm null values have to be managed from the original raw data set.
Another aspect is that the data set should be formatted in such a way that more than one Machine Learning and Deep Learning algorithm are executed in one data set, and best out of them is chosen.


## ALGORITHM:
STEP 1:Importing the libraries<BR>
STEP 2:Importing the dataset<BR>
STEP 3:Taking care of missing data<BR>
STEP 4:Encoding categorical data<BR>
STEP 5:Normalizing the data<BR>
STEP 6:Splitting the data into test and train<BR>

##  PROGRAM:
```
#import libraries

import pandas as pd
import io
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import MinMaxScaler
from sklearn.model_selection import train_test_split

#Read the dataset from drive
d=pd.read_csv("Churn_Modelling.csv")
# Finding Missing Values
print(d.isnull().sum())

#Check for Duplicates
print(d.duplicated().sum())

#Detect Outliers
plt.figure(figsize=(6,4))
sns.scatterplot(x='Age', y='Exited', data=d)
plt.title('Scatter plot of Age vs. Exited')
plt.show()

#Normalize the dataset
# Create an instance of MinMaxScaler
scaler = MinMaxScaler()

# Define the columns to be normalized
columns = ['CreditScore', 'Age', 'Tenure', 'Balance', 'NumOfProducts', 'EstimatedSalary']

# Normalize the specified columns
d[columns] = scaler.fit_transform(d[columns])

# Display the normalized dataset
print("NORMALIZED DATASET\n",d)

#split the dataset into input and output
X = d.iloc[:,:-1].values
print("INPUT(X)\n",X)
y = d.iloc[:,-1].values
print("OUTPUT(y)\n",y)

#splitting the data for training & Testing
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

print("X_train\n")
print(X_train)
print("\nLenght of X_train ",len(X_train))
print("\nX_test\n")
print(X_test)
print("\nLenght of X_test ",len(X_test))
```


## OUTPUT:
### Missing Values:
![image](https://github.com/naveenaakumarasamy/Ex-1-NN/assets/113497406/9b7f999d-877a-49e2-8dff-6501740fe2f1)
### Duplicates:
![image](https://github.com/naveenaakumarasamy/Ex-1-NN/assets/113497406/5f0460f3-bb10-4036-b130-eca053958b76)
### Outliers
![image](https://github.com/naveenaakumarasamy/Ex-1-NN/assets/113497406/04625f01-f8e0-48cc-a9e7-dce8b2f1ba01)

### Normalized dataset:
![image](https://github.com/naveenaakumarasamy/Ex-1-NN/assets/113497406/21a12fef-123d-4101-ae03-e80ccb218377)
### Input and Output
![image](https://github.com/naveenaakumarasamy/Ex-1-NN/assets/113497406/7b066e91-8966-4258-aedb-efb5fd82351d)
### Training and Testing data:
![06](https://github.com/naveenaakumarasamy/Ex-1-NN/assets/113497406/5c2a4d64-cc38-4948-91d8-d45c9f00ecb9)




## RESULT:
Thus, Implementation of Data Preprocessing is done in python  using a data set downloaded from Kaggle.


