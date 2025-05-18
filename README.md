# Implementation-of-K-Means-Clustering

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: REVANTH.P
RegisterNumber:  212223040143
*/

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv(r'Mall_Customers.csv')

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
plt.title("Customer Segments")

```

## Output:

Head()

![326326132-7c884c3f-0e7f-45ff-8145-163228e48127](https://github.com/user-attachments/assets/c90f6a2f-30b5-48bd-bebf-2f7e8a91e53b)

Info()

![326326178-f86d447a-d2d4-4e5c-88e4-3cd74e18198e](https://github.com/user-attachments/assets/7b0134e1-b9da-4e1a-9dca-9bea49bf9446)

isnull.sum()

![326326210-63ae7533-b9f2-46ad-bd50-6c333a4fa5d0](https://github.com/user-attachments/assets/c7f0c5c1-c07b-4ece-a5ce-2a1e312f1d55)

Elbow Method 

![326326253-66266a1c-c893-493b-a5f4-b2f6243fa070](https://github.com/user-attachments/assets/97b1954a-c396-4294-ba70-63965ca3da5d)

Fitting the no. of clusters

![326326285-a5570fc4-bfad-498e-b97d-f80a85e5e5b8](https://github.com/user-attachments/assets/ec45ca93-cd4f-4d9e-b34d-fc8ffc3e79c1)

Prediction of Y

![326326306-e70b8c6a-e5d6-433d-8348-5769b1612a83](https://github.com/user-attachments/assets/7beb38ef-fe3e-4223-b89a-66321cd906e0)

Customer Segments

![326326351-a6adf032-80e7-4055-9fac-feaaacba1115](https://github.com/user-attachments/assets/fb2c24af-ce5d-4f44-afc2-cb34718c03a3)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
