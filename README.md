# Implementation of K-Means Clustering for Customer Segmentation

# AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

# EQUIPMENTS REQUIRED:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

# ALGORITHM:
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program.

# PROGRAM:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: yashaswi.m
Register Number: 212221230062  
*/
```

```
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

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
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

# OUTPUT:
![image](https://user-images.githubusercontent.com/94619247/204450411-44485c0a-12b6-4db8-8014-b407f5d2ba60.png)
![image](https://user-images.githubusercontent.com/94619247/204450441-0af19091-5f91-4bf9-9ee5-ea23cf8af890.png)
![image](https://user-images.githubusercontent.com/94619247/204450460-edb96e50-fffd-4084-afab-004581ec7739.png)
![image](https://user-images.githubusercontent.com/94619247/204450484-e46eb89f-9d17-4d6d-87d3-e753076baf06.png)
<img width="443" alt="image" src="https://user-images.githubusercontent.com/94619247/204450670-c5797122-11cd-4a4d-a31b-965e6d5e9971.png">




# RESULT:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
