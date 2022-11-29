# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import dataset and print head,info of the dataset

2.check for null values

3.Import kmeans and fit it to the dataset

4.Plot the graph using elbow method

5.Print the predicted array

6.Plot the customer segments


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SV.DEEPIKA
RegisterNumber:  212220040161

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No.of.clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("customer segments")
*/
```

## Output:
![exp 8 1](https://user-images.githubusercontent.com/114275126/204444936-5fcb3bff-3834-4689-a3fe-3beb2258692a.PNG)
![8 2](https://user-images.githubusercontent.com/114275126/204450727-0abde376-1175-4eec-861d-51e6e0d66402.PNG)
![8 3](https://user-images.githubusercontent.com/114275126/204450756-e83df710-c358-4c8e-b089-a498da99a12f.PNG)
![8 4](https://user-images.githubusercontent.com/114275126/204450802-61b4453c-f4e9-4780-ae09-7642fb6a2725.PNG)
![8 5](https://user-images.githubusercontent.com/114275126/204450830-c3a3bb56-11c7-462a-8f75-945ec775d26e.PNG)
![8 7](https://user-images.githubusercontent.com/114275126/204451193-c7713bac-ffc7-4724-90f1-6d7ad16559e5.PNG)
![8 8](https://user-images.githubusercontent.com/114275126/204451197-72a05385-13be-4c36-871a-e6b36e01e6c8.PNG)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
