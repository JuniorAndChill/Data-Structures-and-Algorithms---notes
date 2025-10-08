# Algs/Data class 17 Sept 2025

# Big O (space/time complexity)

# Agenda

- Describe efficiency and complexity of designing algorithms
- Apply Big O notation to describe an algorithm's efficiency
- measure an algorithm's best, worst, and average-case time requirements as function of size
- Determine the space complexity of algorithm


## Efficient Algorithms

-When constructing the solution to a problem, you might try different strategies and find that more than one is successful
- Choose between different solution
	- memory
	- time and memory

### Analyzing Algorithms
- defined: 
	- based on time to process solution
- Profiling defined: 
	- Time based on other factors 
	- input-dependent

### Complexity of an Algorithm
- time complexity: 
	- measuring computational time (approximation)
- Fibonacci (programming constructs requires varying amounts of inputs)
- The average input number is directly related to average running time

## Big O Notation
- the growth rate of a function f(n)


## More Big O

- Notation is a way to measure an algorithm 


## More and more Big O 

- Complexity: (n)umber of inputs
	-Linear complexity
	- 





## Linear complexity O(n)

- proportional growth
- worst case scenario
- practical example ....Single loop
- input Size is key

## Logarithmic complexity O(log n)

- Sublinear growth 
- halving principle
- base of the logarithm
	- binary search
	- binary tree search

## Constant complexity O(1)

- Fixed operations
- independence from input size
- most efficient 
- examples of O(1) operations
- Accessing an element in an array by its index
- adding or removing an element at the end of a dynamic array (like push() or pop() in many languages)
- inserting or deleting a node at the beginning of a singly linked list
- basic arithmetic operations
- looking up a value in a hash table (on average)

## Quadratic complexity O(n<sup>2</sup>)

- growth rate
- common scenarios
- examples of algorithm (bubble sort, selection sort, insertion sort, etc)
- implication on performance

## exponential complexity O(2<sup>n</sup>)

- Rapid growth (don't do it)
- recursive structures (recursive Fibonacci)
- examples of implementation

## Comparing Functions for big numbers

- Using the growth rate to analyze algorithms is convenient because:
	- Determining the growth rate of a function is part of a mathematical method

## Upper bounds for functions

- big o notation gives an asymptotic upper bound for a function
	* This upper bound defines a function that will be greater than the result of a 



## Upper bounds for  functions