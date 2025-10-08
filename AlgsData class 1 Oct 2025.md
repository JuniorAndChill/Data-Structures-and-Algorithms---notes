# Algorithms/Data class 1 Oct 2025

# Intro to Search Algorithms

- Data structures why?

- The search process

- records or nodes

- search algorithm

- key = a set of fields used to compare two objects in search and sort algorithm

- target value



* Records are sorted using alphabetical order 

- *Most likely* Every time you want to search you have to sort (optimized way)

## Finding a friend's phone number

- When searching for a friend's contact information on your phone, you most likely use a search algorithm
	-In most modern devices, more than one type of algorithm and a significant number of data structures are used

## Sorted and Unsorted searches

- When implementing a search algorithm, it is essential to know whether the records are sorted
	- sorted (most algorithms will have to sort 1st due to optimization)
	- unsorted (can happen but nobody does this)
## Sequential Search

- linear search, where the data structure is traversed until the record with the matching key is found

## Sequential search algorithms

- suppose x is an array of integers and target is the target value
	- An implementation of a sequential search algorithms that returns the index of the first occurrence of the target value is described as:
```py
	sequential_search(x, target)
	   N = len(x)
	   for j = 0 to N-1 step 1
		if x[j] = target
		   return j
	   return Null
```
- time complexity is dependent on if sorted or not, O(n), *typically will be*
- space complexity is O(1) *will always be this because you'll never add to this*

## Binary (**interval**) search

- there's an expectation that the `arr` is already sorted

- finds the target value by splitting the array in two at each iteration and chooses left or right

- O(1) in best case 

- this search doesn't need to check every element in a data structure, even if it's not present

- also used when inserting a value on a sorted search (more optimized approach)

- Binary search algorithm:
```py
	binary_search(x, target)
	   current_low = 0
	   current_high = len(x)-1

	   while current_low <= current_high
		mid = integer ((current_low + current_high)/2)

		if X [mid] = target 
		   return mid
		else
		   if X [mid] > target
			current_high = mid -1
		   else
			current_low = mid + 1
	   return Null
```

- Time complexity O(log N)
- space complexity non-recursive O(1) | recursive O(log N)


## Recursive Binary Search Method

- simplest case in binary search method is when the array has only one element
	- in such a case, the only thing to do is to compare the element to the inside of 

## 