# Arrays vs List vs Tuple in Python

This repository explains the differences between **Arrays**, **Lists**, and **Tuples** in Python. It includes detailed comparisons, use cases, performance analysis, and example code to help you understand when and why to use each data structure.

---

## 📌 Table of Contents

- [Overview](#overview)
- [1. Python List](#1-python-list)
- [2. Python Tuple](#2-python-tuple)
- [3. Python Array](#3-python-array)
- [Comparison Table](#comparison-table)
- [Performance Benchmarks](#performance-benchmarks)
- [Use Cases](#use-cases)
- [Code Examples](#code-examples)
- [Conclusion](#conclusion)

---

## 🧠 Overview

Python offers multiple ways to store collections of items. Three of the most commonly used are:

- **List**: A dynamic, mutable, and ordered collection.
- **Tuple**: An immutable, ordered collection.
- **Array**: A fixed-type, more memory-efficient alternative from Python's `array` module.

Understanding the difference between them helps write more efficient and readable code.

---

## 1. Python List

- Mutable (can be changed)
- Can hold heterogeneous data types
- Dynamic in size
- Syntax: `my_list = [1, 2, 3]`

## 2. Python Tuple

- Immutable (cannot be changed once created)
- Faster than lists due to immutability
- Can also hold heterogeneous data types
- Syntax: `my_tuple = (1, 2, 3)`

## 3. Python Array

- Provided by the `array` module
- Stores only **homogeneous** data types
- More memory-efficient than lists for numeric data
- Syntax:
  ```python
  from array import array
  my_array = array('i', [1, 2, 3])
![image.png](attachment:a99113d5-c782-42aa-b5f4-fefa5254290f.png)
