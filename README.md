# EX 04 MULTIVARIATE ANALYSIS
### Aim:
To perform Multivariate EDA on the given data set.
### Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
### Algorithm:
- Step1: Import the built libraries required to perform EDA and outlier removal.
- Step2: Read the given csv file.
- Step3: Convert the file into a dataframe and get information of the data.
- Step4: Return the objects containing counts of unique values using (value_counts()).
- Step5: Plot the counts in the form of Histogram or Bar Graph.



### Program:
- SuperStore.csv
```
import pandas as pd
import seaborn as sns
from scipy import stats
import matplotlib.pyplot as plt
df=pd.read_csv('SuperStore.csv')
df.describe()
df.isnull().sum()
df.info()
# FILLING NULL VALUES
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
sns.boxplot(df)
sns.scatterplot(x=df['Region'],y=df['Sales'])
plt.figure(figsize=(10,3))
sns.barplot(x=df['State'],y=df['Sales'])
plt.xticks(rotation=90)
sns.heatmap(df.corr(),annot=True)
sns.displot(df,x='Region',hue="Category")
```
- Output: (SuperStorE.csv)
  
![WhatsApp Image 2023-10-11 at 16 23 47_70c0b7e8](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/d23b9d0f-5860-4772-b3a8-fe3a41f6a203)

![WhatsApp Image 2023-10-11 at 16 24 20_6ec1b4aa](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/13acf2d6-4959-4e08-8892-6c71ca1c41c8)

![WhatsApp Image 2023-10-11 at 16 24 32_a6e4d80e](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/92ba610a-9bff-4c19-85c4-aa46c4f52ffb)


![WhatsApp Image 2023-10-11 at 16 24 45_7b71e7e4](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/7c49a57f-777b-4bd1-a06c-cd9e1a269a3d)


![WhatsApp Image 2023-10-11 at 16 24 58_9cf96542](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/8c9ad395-b524-465d-9971-7f5d5dc8c458)


![WhatsApp Image 2023-10-11 at 16 25 11_a612bf38](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/78b9d814-1a4c-40c1-bbe7-b1eb7cad9eab)


![WhatsApp Image 2023-10-11 at 16 25 25_a28a9eed](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/3f0ca3a9-1736-4961-be60-976788f25bb2)


![WhatsApp Image 2023-10-11 at 16 26 37_1793512e](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/15e43568-5b22-45d4-9b1d-71379d03b0ba)

- Diabetes.csv
```
import pandas as pd
import seaborn as sns
from scipy import stats
import matplotlib.pyplot as plt
df=pd.read_csv('diabetes.csv')
df.describe()
df.isnull().sum()
# REMOVING OUTLIER
z = np.abs(stats.zscore(df['Glucose']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['BloodPressure']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['SkinThickness']))
df=df[(z<3)]
z = np.abs(stats.zscore(dfc['BMI']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Insulin']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['DiabetesPedigreeFunction']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Age']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Outcome']))
df=df[(z<3)]
sns.boxplot(data=dfc)
plt.xticks(rotation=90)
sns.boxplot(data=dfc)
plt.xticks(rotation=90)
sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])
Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)
sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])
sns.displot(df, x="Glucose", hue="Outcome")
df.corr()
sns.heatmap(df.corr(),annot=True)
```
- Output (Diabetes.csv):

![WhatsApp Image 2023-10-12 at 13 07 17_1113ee76](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/3e6db947-d1f8-4696-afb4-da35940c1dc5)


![WhatsApp Image 2023-10-12 at 13 07 33_063ebca2](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/2d0ad1fb-5c26-4270-ac3b-04acb58cf317)


![WhatsApp Image 2023-10-12 at 13 07 46_c883b747](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/439b8d3f-6796-4f2c-9a80-0d28151e1120)


![WhatsApp Image 2023-10-12 at 13 07 59_d14ba51f](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/c5a274b1-049d-41da-9b76-04fbff9f52ed)


![WhatsApp Image 2023-10-12 at 13 08 16_bda86dfa](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/0816cbc8-71c6-4976-8341-fc1c064fbcab)


![WhatsApp Image 2023-10-12 at 13 08 31_1f3d3c37](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/f0debc93-6fc4-4b98-84b1-af2373df2cd0)


![WhatsApp Image 2023-10-12 at 13 09 08_23f5171b](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/5aadfaab-59a8-4742-bd1a-0bf8c4fb914d)


![WhatsApp Image 2023-10-12 at 13 09 25_0f615952](https://github.com/22002102/ODD2023-Datascience-Ex-04/assets/119091638/4e4a0bec-3eb6-4210-a7b6-ed86e590344f)

### RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.
