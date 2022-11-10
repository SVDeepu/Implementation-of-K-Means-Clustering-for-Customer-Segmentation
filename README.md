# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
Step1:
Import the required packages.

Step2:
Import the dataset to work on.

Step3:
From sklearn module import kmeans.

Step4:
Define number of clusters to be made.

Step5:
Assign the cluster values.

Step6:
Plot the cluster using matplotlib.pyplot

Step7:
End the program.
```

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: N.YASASWINI
RegisterNumber:212220040095
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11): 
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
  plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
![image](https://github.com/NYasaswini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/047df608e778d722dd30d1f3c128b2be3f86e2c8/WhatsApp%20Image%202022-11-10%20at%2009.06.10.jpg)
![image](https://github.com/NYasaswini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/1d36eb448e9dee1705e5a3c0aaa930e82407c547/WhatsApp%20Image%202022-11-10%20at%2009.06.11.jpg)
![image](https://github.com/NYasaswini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/6a87c5b7e80744a3f11ebe925b9a85f162bc975f/WhatsApp%20Image%202022-11-10%20at%2009.06.12.jpg)
![image](https://github.com/NYasaswini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/23311eca314f89be3bfb1f995c1265339a4c6d68/pic4.jpg)
![image](https://github.com/NYasaswini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/2914d582bfefe1882a579ee012828c884a558687/pic5.jpg)
![image](https://github.com/NYasaswini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/f437d8da7a7a96a9aa3d4a92fe9ba095ada8a743/pic6.jpg)
![image](https://github.com/NYasaswini/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/blob/8e2def3b0cb0ee55d793177d592440a577f18f46/pic7.jpg)
## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
