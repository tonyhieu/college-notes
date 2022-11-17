---
toc: true
layout: post
description: ICS 6B Chapter 6.6-6.10
categories: [ics6b, reading, fall22-23, markdown]
title: Matrices and More on Relations
---

## 6.6: Matrix multiplication and graph powers

- A **matrix** is a 2d array with rows and columns; each element in a matrix is called an **entry** and each entry can be denoted by i, j where i is the row and j is the column
    - A matrix is a **square matrix** if the number of rows and columns are the same
- An **adjacency matrix** can be created for a directed graph with n vertices; the matrix will have n rows and columns, and each entry will either be 1 or 0 if there is an edge from vertex i to vertex j
- You can apply mathematical operations onto a matrix
    - A **Boolean matrix** is a matrix whose entries only contain elements from {0, 1}, and you can use Boolean addition/multiplication/whatever on entries of a Boolean matrix
    - The product of two matrices, A and B, is well defined if the number of columns in A is equal to the number of rows in B
    - To find A x B, take the **dot product** of a row of A and a column of B
        - If A and B are n x n matrices, then the dot product is represented by the following equation: A<sub>i, 1</sub>B<sub>1, j</sub> + A<sub>i, 2</sub>B<sub>2, j</sub> + ... + A<sub>i, n</sub>B<sub>n, j</sub>
        - Illustration: ![Screen Shot 2022-11-14 at 4 39 07 PM](https://user-images.githubusercontent.com/54915685/201797821-daa78966-a44b-4055-ae7e-1249efbed029.png)
    - A **matrix product**, or AB, is found by taking the dot product of row i of matrix A and column j of matrix B
        - Example: ![image](https://user-images.githubusercontent.com/54915685/201819646-f544e50a-9678-4a58-9361-8d2c3f7961b6.png)
        - Continue the process throughout the matrix: ![image](https://user-images.githubusercontent.com/54915685/201819707-04dad7b3-6cac-4313-9efe-c6d10550079c.png)
- The k<sup>th</sup> **power of a matrix** is the product of k copies of A
    - A<sup>k</sup> = A * A * ... * A, k times
- Can take the power of a matrix and apply it to the power of a directed graph
    - Take a graph, G, and create an adjency matrix (A) for it
    - Compute A<sup>k</sup>
    - A<sup>k</sup> is the adjacency matrix for G<sup>k</sup>
- The **matrix sum** of two matricies with the same number of rows and columns is calculated by adding each entry and calculating the resulting matrix
    - Example: ![image](https://user-images.githubusercontent.com/54915685/201821566-b4970a66-cd57-494e-a177-993cc68ac37d.png)
    - The matrix sum can be used to find the graph union between two graphs
        - Example: ![image](https://user-images.githubusercontent.com/54915685/201821798-7ef79109-1c2a-4598-a296-f388ae832bc2.png)
    - The transitive closure of a directed graph can be found by adding a matrix's powers up to its number of vertices
        - Equations: ![image](https://user-images.githubusercontent.com/54915685/201822468-d87e5b27-f031-43fa-8a4b-1737ee7b1930.png)

## 6.7: Partial orders
