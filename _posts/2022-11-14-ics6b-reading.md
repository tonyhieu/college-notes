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

- A **partial order** must satisfy three conditions
    - Transitive
    - Reflexive
    - Anti-Symmetric
- Example: ![image](https://user-images.githubusercontent.com/54915685/202606531-14c9507f-e29f-4d36-8168-e328fea6caad.png)
- Partial orders are similar to <= in the sense that certain elements can be "less than" another element by being the the tail of an edge
- Two elements are **comparable** if they have an edge between them and **incomparable** if not
    - To represent the relation, a ⪯ b is used instead of aRb (note the curved part of the < sign)
    - A partial order is a **total order** if all elements are comparable with each other
- A **minimal element** is one with no elements pointing into it, while a **maximal element** is one with no edges pointing out of it
- A **Hasse diagram** represents a partial order on a finite domain
    - Drawn by putting lower elements below higher ones
    - Example: ![image](https://user-images.githubusercontent.com/54915685/202605597-1244b764-6d55-41be-b79d-99ef859096e9.png)

## 6.8: Strict orders and directed acyclic graphs

- A **strict order** is similar to a partial order, must satisfy two conditions
    - Transitive
    - Anti-Reflexive
    - Based on the above two properties, a strict order is also anti-symmetric
- Example: ![image](https://user-images.githubusercontent.com/54915685/202606631-eb5f079c-8ba6-4be8-bf79-ac366d2d254a.png)

- Strict orders are analagous to < because you cannot be "equal" to yourself (anti-reflexive)
- Strict orders are closely related to **directed acyclic graphs (DAG)** which are directed graphs with no cycles
    - A directed graph, G, has no cycles if and only if G<sup>+</sup> is a strict order
- A **topological sort** is taken by starting with the minimal element(s), putting them into a list, and then removing them from the graph to get the new minimal element(s)

## 6.9: Equivalence relations

- An **equivalence relation** (represented by a ~) must satisfy three conditions
    - Transitive
    - Reflexive
    - Symmetric
- Example: ![image](https://user-images.githubusercontent.com/54915685/203151144-24bf4efd-99d0-4ba2-8a76-f2ca9aea5366.png)
- An **equivalence class** is a subset of the domain that that contains a certain kind of element
    - Represented by \[a\] where a represents the properties of that class
    - Example: ![image](https://user-images.githubusercontent.com/54915685/203151773-eb0ebf74-737e-47a9-bf5c-f3af790c78c8.png)
    - Two different equivalence classes can either be identical or completely disjoint
- A **partition** of set A is a set of non-empty subsets of A that are pairwise disjoint and whose union is A
    - The union of all equivalence classes will create a partition

## 6.10: N-ary relations and relational databases
- An **n-ary relation** is a relation on multiple sets A<sub>1</sub>, A<sub>2</sub>, ... , A<sub>n</sub> which is a subset of A<sub>1</sub> x A<sub>2</sub> x ... x A<sub>n</sub>
- A **database** is a collection of records, and the **relational database model** stores data records as relations
    - The type of data stored in each entry of the record, represented by an n-tuple, is called an **attribute**
    - A **query** to a database requests for a particular set of data
    - A **key** is one or more attributes that uniquely identifies each n-tuple in the database
- **Selection** chooses n-tuples based on their attributes
    - Examples: ![image](https://user-images.githubusercontent.com/54915685/203152996-18fe95b2-a9ec-46dc-b80b-e44cbfcc8b76.png)
- **Projection** removes all attributes that are not specified in the projection
    - Example: ![image](https://user-images.githubusercontent.com/54915685/203153243-bd156fab-c494-4551-8cb1-4f1797712cde.png)
