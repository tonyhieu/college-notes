---
toc: true
layout: post
description: ICS 6B Reading Notes
categories: [ics6b, reading, fall22-23, markdown]
title: ICS 6B Chapter 3
---

## 3.1: Sets and subsets

- **Set**: A collection of objects (or **elements**); may contain different types of objects (animal, number, book, etc.)
    - **Roster notation**: Directly listing all of the elements in a set using curly braces
        - Order is unimportant, and repeating an element doesn't change the set
        - { 1, 2, 3, 4 }, { 4, 2, 3, 1 }, and { 1, 1, 2, 3, 4 } are all the same
- ∈ is used to show that an element is in a set (2 ∈ A), while ∉ shows that an element is *not* in a set (5 ∉ A)
- **Empty set or null set**: The set with no elements, represented by ∅; can be denoted as {}
    - For any element a, a ∉ ∅ is true
- **Finite set**: A set that is empty or whose elements can be numbered from 1 to some integer n
    - **Cardinality**: The number of distinct elements in a set, denoted by \|\|
        - \|A\| reads as "the cardinality of A"
- **Infinite set**: A set that is not finite; unlimited number of elements
- Can denote a set using ellipses (...)
    - B = { 1, 3, 5, ... , 99 } is a set of odd numbers between 1 and 100, inclusive
    - C = { 3, 6, 9, 12, ... } is a set of all multiples of 3
- Two sets are equal if they have the same elements; if, for any element a, a ∈ D if and only if a ∈ E
- Common sets
    - N: the set of all natural numbers (integers greater than or equal to 0)
    - Z: the set of all integers
    - Q: the set of all rational numbers
    - R: the set of all real numbers
    - A + or - in the superscript changes it to all positive or negative elements in the set
        - Positive is > 0, negative is < 0, and non-negative is >= 0
- **Set builder notation** specifies a set from an existing set
    - Colon is used to represent "such that" (similar to how colon works as an if statement)
    - Ex: C = { x ∈ Z : 0 < x < 100 and x is prime} means that C is the set of all prime numbers between 0 and 100, exclusive
- **Universal set**: Set containing all elements in a particular context
    - Sets may be depicted using **venn diagrams**
- A set is a **subset** of another set if every one of its elements is contained in the other set
    - Denoted by ⊆; ⊈ is used if a set is not a subset of another
    - { 1, 2, 3, 4 } is a subset of { 1, 2, 3, 4, 5 }
    - Two sets are equal if they are both subsets of each other
- A **proper subset** of another set means that the larger set contains elements that the subset doesn't
    - Denoted with ⊂

## 3.2: Sets of sets
- A set can contain multiple sets within it; think of it as nested lists
    - If x ∈ set A, then { x } ∈ set A
- A **power set (P(x))** contains all subsets in another set
    - If A = { 1, 2, 3 }, then P(A) = { ∅, { 1 }, { 2 }, { 3 }, { 1, 2 }, { 1, 3 }, { 2, 3 }, { 1, 2, 3 } }
    - The cardinality of a power set is 2 to the power of the cardinality of the original set

## 3.3: Union and intersection
- The **intersection** of two sets (denoted by ∩) is a set containing all elements shared by both sets
- The **union** of two sets (denoted by ∪) is a set containing all elements in both sets

## 3.4: More set operations
- The **difference** of two sets (denoted by -) is the set of elements in one set but not the other (asymmetric)
    - Ex: A - B is the set of elements in A but not B
- The **symmetric difference** of two sets (denoted by ⊕) is the set of elements in one set but not the other (symmetric)
    - Ex: A ⊕ B is the set of elements in A and B but not each other
- The **complement** of two sets (denoted by an over bar) is the set of elements in the universal set but not in the given set
    - If U = Z and A = { x ∈ Z: x is odd }, then the complement is all even integers

![image](https://user-images.githubusercontent.com/54915685/196336415-2a78dea5-5551-4a5a-a592-b8f5a5db2a8e.png)

## 3.5: Set identities
- A **set identity** is a equation that is true regardless of the elements in a set
- SImilar to other identities

![Screen Shot 2022-10-17 at 9 50 00 PM](https://user-images.githubusercontent.com/54915685/196338152-9497dc6d-f7ac-43a2-9b78-b86811cee67e.png)

## 3.6: Cartesian products
- **Ordered pair**: written (x, y) and contains two **entries**; the parantheses means that order matters
- The **Cartesian product** (denoted by X) of two sets is the set of all ordered pairs where the first entry is equal to elements in the first set and the second entry is equal to elements in the second set
    - Ex: ![Screen Shot 2022-10-17 at 9 57 27 PM](https://user-images.githubusercontent.com/54915685/196339067-c7167ab2-2aba-465b-bdec-34c07e58aa37.png)
- An **ordered triple** is an ordered list of three items, and an **ordered n-tuple** is an ordered list of n items
- A superscript denotes all ordered tuples in a set; R<sup>2</sup> denotes all ordered pairs in the set of real numbers
- **Strings**, or ordered tuples with letters, can be written without parantheses or commas
    - Ex: if A = {x, y}, the set A<sup>2</sup> would be { xx, xy, yx, yy }
- A **binary string** is a string with letters taken from { 0, 1 }, and a **bit** is one character
    - A string of length n is called an **n-bit string**
- An **empty string** (denoted by λ) has a length of 0
- **Concatenation** of two strings is adding them together

## 3.7: Partitions

- Two sets are **disjoint** if they share no comment elements (or if A ∩ B = ∅)
    - A sequence of sets is **pairwise disjoint** if every set in the sequence is disjoint to each other
- A **partition** of a set is a collection of subsets that create a pairwise disjoint sequence of sets
    - Example: ![Screen Shot 2022-10-17 at 10 16 56 PM](https://user-images.githubusercontent.com/54915685/196341532-0c308220-c311-4fa5-aee4-1777538ad47d.png)