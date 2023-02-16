---
toc: true
layout: post
description: ICS 6D Chapter 10.5-10.12
categories: [ics6d, reading, winter22-23, markdown]
title: Counting Subsets and Multisets
use-math: true
---

## 10.5: Counting subsets

- A subset of size r is called an **r-subset**, or an **r-combination** in the context of counting

**Using the k-to-1 rule to count subsets**

- From a set of size 5, if you want to choose 3 elements, there are 5!/2! ways to do so
    - We don't care about order, so we must divide 5!/2! by 3! in order to get rid of duplicate subsets
    - Thus, the choose notation is created: $$ {{n \choose r} = {{n!} \over {r!(n-r)!}} } $$
    - Additionally, $$ {{n \choose r} = {n \choose n - r} } $$
- Example of using choose notation to count paths on a grid: ![image](https://user-images.githubusercontent.com/54915685/219250800-4c4ae318-dc86-4d53-a69a-dadacdc67679.png)

## 10.6: Subset and permutation examples

- Typically, we count subsets when the ordering of the elements in the subset do not matter (sometimes marked as indistinguishable, or identical) but permutations when the ordering does matter (sometimes marked as distinguishable)
- Example showing the difference: ![image](https://user-images.githubusercontent.com/54915685/219251331-869f1dda-f586-4f98-9c3e-85f8d1c5e6ae.png)

## 10.7: Counting by complement

- To count by complement, we can subtract the number of elements that DO NOT have a desired property from the original set from the number of elements in the original set
    - In other words: $$ {|P| = |S| - |\overline{P}|} $$

## 10.8: Permutations with repetitions

- A **permutation with repetition** is the ordering of a set of items where some elements may be repeated, such as the scrambling of repeated letters in a word
    - Example of counting the number of permutations in MISSISSIPPI: ![image](https://user-images.githubusercontent.com/54915685/219251895-4dac3181-d28e-45ed-bd46-0fc41aac6453.png)
- Formula for counting permutations with repetition: ![image](https://user-images.githubusercontent.com/54915685/219252008-f911cb7d-db19-4074-9c6a-dba8cd174b37.png)

## 10.9: Counting multisets

- While a set is a collection of *unique* items, a **multiset** can have multiple instances of the same instances
    - {1, 2, 3} is a set and a multiset, while {1, 2, 2, 3} is a multiset only
- Can use a strategy involving code words to count multisets
    - Suppose that we want to count the number of ways to select 12 cookies from 4 types; the following shows a bijection between a multiset and its corresponding code word: ![image](https://user-images.githubusercontent.com/54915685/219252432-d15d2364-b447-49eb-a9c1-948a35d278cb.png)
    - Thus, the number of ways to select cookies is $$ {{n + m - 1} \choose {m-1}} $$
    - Table representing the values to what they are in the code word: ![image](https://user-images.githubusercontent.com/54915685/219252538-aa49f8d7-c62a-4a31-b9ac-94db0e1aeb26.png)
- In general, the way to select n objects from m varieties can be represented by $$ {{n + m - 1} \choose {m-1}} $$
    - This applies to many problems, including ones where *indistinguishable objects* (such as balls) are distributed amongst *distinguishable objects* (bins)

## 10.10: Assignment problems: Balls in bins

- Table with different ways to organize "balls in bins", or divide objects amongst distinguishable objects: ![image](https://user-images.githubusercontent.com/54915685/219265562-6eacd886-5626-46a8-8f15-8e3f879847e5.png)

## 10.11: Inclusion-exclusion principle

- The **principle of inclusion-exclusion** is used for finding the cardinality of the union of two sets of known cardinalities
    - Defined as $$ {|A \cup B| = |A| + |B| - |A \cap B|} $$
    - For three sets, you must add back the intersection of all sets, so:
        - $$ {|A \cup B \cup C| = |A| + |B| + |C| - |A \cap B| - |B \cap C| - |A \cap C| + |A \cap B \cap C|} $$
- Generally, the principle of inclusion-exclusion can be defined as follows: ![Screen Shot 2023-02-15 at 8 08 27 PM](https://user-images.githubusercontent.com/54915685/219266224-df8dcc4e-7a3f-4073-979a-f053495be793.png)

## 10.12: Counting problem examples

- Counting donut varieties with multiple limits: ![image](https://user-images.githubusercontent.com/54915685/219266309-7409f5fc-f63b-4ba8-9678-25dca2626935.png)
- Counting license plates that match: ![image](https://user-images.githubusercontent.com/54915685/219266350-266d6c78-1f92-44d3-8c5e-7286e00a71ef.png)
