# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas as pd and matplotlib.pyplot as plt
2. Get the info and also obtain the sum of any null values
3. Importing KMeans from sklearn.cluster we group the similar datas
4. Grouping similar datas gives us a elbow shaped graph which is called the Elbow method. 5.Print the number of clusters obtained
5. Giving the clustered data differnet colors and presenting as a scatter plot
6. Print the obtained graph. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Pravinrajj G.K
RegisterNumber:  212222240080
*/

import pandas as pd
import matplotlib.pyplot as plt
data =pd.read_csv("/content/Mall_Customers (1).csv")
**
**
data.head()
**
**
data.info()
**
**
data.isnull().sum()
**
**
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
**
**
km = KMeans(n_clusters = 5)
print("K-Means")
km.fit(data.iloc[:,3:])
**
**
y_pred = km.predict(data.iloc[:,3:])
print("Array:")
y_pred
**
**
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
print("Customer Segments")
print("Customer Segement")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### data.head()
![image](https://github.com/Pravinrajj/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/117917674/0b8c9403-fb30-4532-a512-04fc87785e81)

### data.info()
![image](https://github.com/Pravinrajj/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/117917674/e2bedec8-54c9-4817-b446-e8c352df6dc6)

### data.isnull().sum()
![image](https://github.com/Pravinrajj/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/117917674/bf25fca5-8621-4b90-8e17-ec3503188ea2)

### Graph
![image](https://github.com/Pravinrajj/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/117917674/8a3551d3-c8e7-42d0-8eeb-bd8d81da0f9e)

### K-means
![image](https://github.com/Pravinrajj/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/117917674/79b78b50-5c07-404d-b4af-ae5c30f4fed0)

### y_pred
![image](https://github.com/Pravinrajj/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/117917674/eae6adc9-6d9e-46c3-9483-c802d1c7892c)

### Customer segments
![image](https://github.com/Pravinrajj/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/117917674/8fe78e9b-2ee9-4304-8d88-d88c51204b7e)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
