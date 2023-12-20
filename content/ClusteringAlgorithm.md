---
title: "Clustering Algorithm"
date: 2022-11-20T09:03:20-08:00
draft: false
---
---
---
title: "Clustering Algorithm"
date: 2022-11-20T09:03:20-08:00
draft: false
---

[![Image from Gyazo](https://i.gyazo.com/93840e4485a1fd0de00f4b25ef07f95e.jpg)](https://gyazo.com/93840e4485a1fd0de00f4b25ef07f95e)

1. Data Collection: First, collect the choices (three addresses) that each crowd-worker sent as a response. These choices express the options that the crowd-workers have chosen. Each worker sends their opinions in the form of three addresses.

2. Data Transformation: Next, transform the collected choices into a format of each crowd-worker and their list of choices. Here, the crowd-workers represent rows, and choices represent columns.

3. For example, it will look like this:<br>
Worker1: [Address1, Address2, Address3], Worker2: [Address2, Address3, Address4], Worker3: [Address1, Address3, Address4]

4. Data Matrix Conversion: Then, convert the above data into a matrix. In this matrix, the rows are crowd-workers, the columns are addresses, and the value in each cell indicates whether that crowd-worker has selected that address or not. If they chose it, place 1 in the cell, if not, place 0.

|         | address1 | address2 | address3 | address4 |
|---------|----------|----------|----------|----------|
| worker1 |     1    |     1    |     1    |     0    |
| worker2 |     0    |     1    |     1    |     1    |
| worker3 |     1    |     0    |     1    |     1    |

This matrix is likely to be sparse (that is, most elements are 0). This is because not all crowd-workers will choose all addresses.

Through the above steps, the choices collected from crowd-workers are transformed into a matrix. This matrix serves as a foundation for analyzing the similarity and differences in the responses among the crowd-workers while representing the choices of the crowd-workers. Also, this matrix is used as input for further analysis methods such as dimensionality reduction and clustering.
