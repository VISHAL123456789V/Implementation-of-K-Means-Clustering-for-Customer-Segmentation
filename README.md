# Ex-8 : Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Start the program

2.Import pandas and matplotlib.pyplot.

3.Read the dataset and transform it.

4.Import KMeans and fit the data in the model.

5.Plot the Cluster graph.

6.End the program


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Vishal T
RegisterNumber:  212223100060
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square.
for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
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
plt.title("Customer Segments")
```

## Output:

data.head() function

![image](https://github.com/23012647/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568857/6e5299f4-6f89-4c71-8bce-39f38673b955)

data.info()

![image](https://github.com/23012647/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568857/10c17bc7-612b-441a-a7e4-16e9e9fecf34)

data.isnull().sum() function

![image](https://github.com/23012647/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568857/5108197c-455b-4ba1-8420-db0a05935e50)

Elbow method Graph

![image](https://github.com/23012647/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568857/a7df9c2c-d26e-45e8-b5d4-fbcf890f0625)

KMeans clusters

![image](https://github.com/23012647/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568857/255661ef-85c2-4382-8b83-d159e05d1e00)

![image](https://github.com/23012647/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568857/77bfaee8-fb1e-485a-a46c-bf6e35d009ba)

Customer segments Graph

![image](https://github.com/23012647/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568857/fb70157f-8859-494e-af78-ecd0e2a63455)











## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
