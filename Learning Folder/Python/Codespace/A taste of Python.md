# Functions

> A pieces of code to perform some certain operations
###### table showing basic operations-

|   Operations   | Sign |
|:--------------:|:----:|
|    Addition    |  +   |
|    Division    |  /   |
| Exponentiation |  **  |
| Multiplication |  *   |
|  Substraction  |  -   |

 These are some inbuilt operations for the Python programming language to use.
#### *Now if the need is to use **complex mathematical expressions*** then we have use something called **Modules**. 
- A _module_ is a group of code items such as functions that are related to one another. Individual modules are often in a group referred to as a _library_.
- Modules can be loaded using `import`. Functions that are part of the module **`modulename`** can then be used by typing **`modulename.functionname()`**. For example, **`sin()`** is a function that is part of the `math` module, and used by typing **`math.sin()`** with some number between the parentheses.
- Within a given Jupyter Notebook the variables you define earlier in the notebook will be available for use in the cells that follow as long as you have already executed the cells.
- Modules may also contain constants such as `math.pi`. 
---
# Variables

> as simply can be put, like in algebra variables are such expressions which doesn't have any pre-defined values, rather the other definitive values can be stored and used for the calculations.

In the python program simply assigning value to variables is straightforward. To assign a value, simply **`variable_name = value`**.

---
# Data Types
(**A important topic to understand**) - Book Suggestion - ***Introduction To Algorithms, Third Edition***
### Additional information to understand data types-
To understand data structures, there are several excellent resources available that provide comprehensive explanations and examples. Here are some of the best resources to help you learn and understand data structures:

1. Books:
   - "Introduction to Algorithms" by Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, and Clifford Stein.
   - "Data Structures and Algorithms in Python" by Michael T. Goodrich, Roberto Tamassia, and Michael H. Goldwasser.
   - "Algorithms, Part I" and "Algorithms, Part II" by Robert Sedgewick and Kevin Wayne.

2. Online Courses:
   - Coursera: "Algorithms, Part I" and "Algorithms, Part II" offered by Princeton University.
   - edX: "Introduction to Data Structures" by UC San Diego.
   - Udemy: "Data Structures and Algorithms: Deep Dive Using Java" by Tim Buchalka and Goran Lochert.

3. Websites and Tutorials:
   - GeeksforGeeks (www.geeksforgeeks.org): A popular platform with extensive coverage of data structures, algorithms, and coding problems.
   - Tutorialspoint (www.tutorialspoint.com): Provides tutorials on various data structures with practical examples.
   - Data Structures Easy to Advanced Course - Full Tutorial by freeCodeCamp (www.youtube.com/watch?v=RBSGKlAvoiM): A comprehensive video tutorial explaining data structures from beginner to advanced levels.

4. Online Platforms for Coding Practice:
   - LeetCode (www.leetcode.com): Offers a vast collection of coding problems with a focus on data structures and algorithms.
   - HackerRank (www.hackerrank.com): Provides coding challenges that cover different aspects of data structures and algorithms.

1. Interactive Visualizations:
   - Visualgo (visualgo.net): A website that provides animated visualizations of various data structures and algorithms.
   - Data Structure Visualizations by USFCA (www.cs.usfca.edu/~galles/visualization): Another collection of interactive visualizations for different data structures.

There are four basic type of data types used in a program.

| Data type name | Data Type            | Example     |
|:--------------:| -------------------- | ----------- |
|      **int**       | Whole integer values | 4           |
|     **float**      | Decimal values       | 0.5         |
|      **str**       | Character string     | 'Four'      |
|      **bool**      | True/False values    | True, False |

---
# Lists and Indices

> Lists are nothing but arrays of values, and indices are the position of certain value on a list.

Let's say 
```
# there is a list called A,B,C,D
list = [A, B, C, D]
# here there are four values in the list
# now the indices always startswith 0 and ends with -1
# So, the indices of the list will be
indices(list[A, B, C, D])
0, 1, 2, -1
```
