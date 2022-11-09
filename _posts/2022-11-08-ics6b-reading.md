---
toc: true
layout: post
description: ICS 6B Chapter 5
categories: [ics6b, reading, fall22-23, markdown]
title: Binary Relations
---

## 6.1 Introduction to binary relations

- A **binary relation** between two sets A and B is denoted as a subset R of A x B
    - Binary because it is a Cartesian product of two sets
    - For a ∈ A and b ∈ B, the fact that (a, b) ∈ R is denoted by aRb.
    - For example, take a school with a set of students (S) and a set of classes (C); a given student is taking a certain class if sEc
- Relations can be defined on infinite sets using formulas
    - Example: xCy if x + y = 2
- If two sets are finite, then a binary relation between them can be represented by a list of irdered pairs or in an **arrow diagram**
    - Arrow diagram: ![Screen Shot 2022-11-08 at 3 37 37 PM](https://user-images.githubusercontent.com/54915685/200699243-ef8cd999-029b-459f-9e15-4d424141a1bd.png)
- A **matrix representation** of a binary relation can be shown using a 2D array of numbers with \|A\| rows and \|B\| columns
    - If aRb, then the given square is 1; otherwise, it's 0
    - Example: ![Screen Shot 2022-11-08 at 3 39 32 PM](https://user-images.githubusercontent.com/54915685/200699450-70f67448-517e-46f4-81cd-92a3fc77fed9.png)
- Can use a binary relation on two sets which are the same; called a **binary relation on a set**
    - The set is called the **domain** of the binary relation
- In an arrow diagram for a binary relation on a set, if an element maps to itself, it can be represented via a self-loop
    - Example: ![Screen Shot 2022-11-08 at 3 44 16 PM](https://user-images.githubusercontent.com/54915685/200700178-4c718aaf-1f96-4508-84ba-f4a36df843dc.png)

## 6.2 Properties of binary relations
- A binary relation on set is **reflexive** if and only if, for every x in the set, xRx
- A binary relation on set is **anti-reflexive** if and only if, for every x in the set, it is not true that xRx
    - Both properties are universal statements, so to show one or the other, you must show that xRx is true/false for one element
    - If some of the elements are related to themselves and some are not, then the relation is neither reflexive nor anti-reflexive
- A relation on set is **symmetric** if and only if, for every pair x,y, xRy if and only if yRx
    - In other words, xRy and yRx are both true or neither xRy and yRx are true
- A relation on set is **anti-symmetric** if and only if, for every pair x, y, xRy and yRx are not both true
    - In other words, these three conditions are met:
        - xRy, but it is not true that yRx
        - yRx, but it is not true that xRy
        - Neither xRy nor yRx is true
- A relationship is **transitive** if and only if, for every three elements x, y, z, if xRy and yRz then xRz
- Example on how to prove (or disprove) properties: ![Screen Shot 2022-11-08 at 4 00 15 PM](https://user-images.githubusercontent.com/54915685/200702310-37fa5bc0-3059-4195-851e-6a84a94cb54a.png)

## 6.3 Directed graphs, paths, and cycles
- A **directed graph (digraph)** is a way to visualize relations, represented by (V, E)
    - Consists of a set of **vertices**, V, and a set of **directed edges**, E, which is a subset of V x V
    - One element of V is a **vertex**, and an edge (u, v) connects two vertices, with the **tail** vertex being represented by u and the **head** vertex being represented by v
    - If the head and tail are the same, then the edge is a **self-loop**
    - The **in-degree** of a vertex is the number of edges pointing into it (how many times it's the head) while the **out-degree** is the number of edges pointing out of it (how many times it's the tail)
- A **walk** in a directed graph is a sequence of alternating vertices and edges that is used to visualize paths between vertices
    - Takes the form of (v0, (v0, v1), v1, (v1, v2), v2, ...)
    - If there are two consecutive vertices, then the edge between those vertices is assumed to exist
    - The **length** of a walk is the number of edges
    - A **closed walk** is one where the first and last vertices are the same; an **open** one is one where they are not
- A **trail** is an open walk in which no edge occurs more than once
- A **path** is a trail in which no vertex occurs more than once
- A **circuit** is a closed walk in which no edge occurs more than once
- A **cycle** is a circuit of length at least 1 in which no vertex occurs more than once, except the first and last vertices which are the same

## 6.4 Composition of relations
- Can combine two relations using a **composition**, which is denoted S o R
    - A pair (a, c) ∈ S o R if and only if there exists b such that (a, b) ∈ R and (b, c) ∈ S
    - Visual representation: ![Screen Shot 2022-11-08 at 4 25 33 PM](https://user-images.githubusercontent.com/54915685/200705749-205a3f04-d978-4085-9f30-b9d3d8a02aac.png)

## 6.5 Graph powers and the transitive closure
- A relation on set can be composed with itself: R o R
- A composition of the same relation on set repeated can be represented in power notation
    - R<sup>1</sup> = R
    - R<sup>k</sup> = R o R<sup>k-1</sup>, for all k >= 2
- In an edgeset, E<sup>k</sup> is the relation E composed with itself k times, and G<sup>k</sup> is the graph whose edgeset is E<sup>k</sup>
    - The k is denoted as the **power of G**
- The Graph Power Theorem: Let G be a directed graph. Let u and v be any two vertices in G. There is an edge from u to v in Gk if and only if there is a walk of length k from u to v in G.
- Visual Example: ![Screen Shot 2022-11-08 at 4 38 56 PM](https://user-images.githubusercontent.com/54915685/200707432-7c8b1e76-28c2-42b3-ac51-1fab0dbfcc3e.png)
- The union of G<sup>k</sup> represents the reachability of vertices by walks of any positive length in G
    - If the number of vertices is finite, then you need to only add up to the power of \|V\|
- A relation R follows the same structure
    - Let R be a relation on a finite domain with n elements; R<sup>+</sup> = R<sup>1</sup> u R<sup>2</sup> u R<sup>3</sup> u ... u R<sup>n</sup>
    - R<sup>+</sup> is known as the **transitive closure of R**
        - Any relation that contains all pairs from R and is transitive must include all the pairs in R<sup>+</sup>
    - Accordingly, G<sup>+</sup> is the **transitive closure of G**
- Graphical Example: ![Screen Shot 2022-11-08 at 4 46 27 PM](https://user-images.githubusercontent.com/54915685/200708495-39f88648-b4ae-470b-bb8a-72cda78f4038.png)
- You can also find a transitive closure using the following method:
    - Repeat until no pairs can be added to R:
    - If there are three elements x, y, z ∈ A such that (x, y) ∈ R, (y, z) ∈ R and (x, z) ∉ R, then add (x, z) to R

![Screen Shot 2022-11-08 at 4 49 01 PM](https://user-images.githubusercontent.com/54915685/200708836-168ed2e1-3cef-4deb-9203-459c024fdbeb.png)