# Algs/Data class 24 Sept 2025

# Intro to sorting Algorithms

- Sorting algorithms are important
- Data sequencing
- Comparison Function (typically recursive)
	- optimization

## Applied sorting

### Given a video streaming service:
- the number of videos increases with time passes
- you invest in a high-speed server, but the space is insufficient
- you choose to put some videos on the faster server and the rest on the older servers
- how do you decide what videos to put on which servers?
- you need to apply

## What is a sorting Algorithm

- sorting algorithm defined: 
   - sort them based on a set of fields, keys
- a stable sorting algorithm, that retains a relative input order (relative order is preserved)

## Types of sorting algorithms

- several characteristics may be used to classify sorting algorithms

### ...you can
- compare the complexity
- categorize a sorting algorithm by the number of swaps
- use aux memory
- classify sorting algorithms by whether an aglorithm is stable or not

## Bubble sort

- is a simple sorting algorithm that traverses parts of the input array, swapping elements to put the largest of the current sub-array 
   - (it will continue till all rounds are done; i,e, *if 100 elements then 99 sorts*)

## Performance of Bubble sort
```
bubble_sort(x,y)
   top_index = N-1
   while loop
```

## Bubble big O
- time Complexity | best = O(n) | avg = O(n<sup>2</sup>) | worst = O(n<sup>2</sup>) |
- space complexity |  O(1)

## Selection Sort

- is sorting alg that iteratively searches for the smallest element and swaps it into the appropriate place
- it is like bubble but does less swaps since it puts it in the correct place each time
	- you are at the mercy of the memory 
- starts at 1<sup>st</sup> element and puts smallest there then excludes that one in following

## Performance of selection sort

- complexity always | 0(n<sup>2</sup>) 
- space complexity | 0(1) 

## Insertion sort

- is a sorting algorithm that creates a sorted array by sequentially inserting each new piece of data in the appropriate position
- checks if is already sorted; *adaptive sorting*
- checks and moves between elements

## Performance of insertion sort

- time complexity | best = O(n) | avg = O(n<sup>2</sup>) | worst = O(n<sup>2</sup>)
- space complexity | O(1)

## Quicksort

- is a sorting algorithm that divides an array into two parts, then applies the same strategy to each part to sort the whole array
- this means that it uses the strategy of divide and conquer
- quicksort reduces the problem of sorting an array of *N* elements into sorting two arrays with lengths less than *N*
- in comp sci, a pivot value is used to define a start or middle value of an array
- it will recursively find and set pivot values and when it's done everything will be sorted
- it will use "split" to create sub-arrays to perform the algorithm
- worst performance will come from pre-sorted data
- time complexity | best = O(n) | avg = O(n log n) | worst O(n<sup>2</sup>) |
- space complexity | O(1)

## Merge sort 

- is not in-place sorting algorithm that splits an array recursively into smaller parts 
   - each part is sorted and then the parts are joined to produce the desired position
- aux array will end up being the final outcome array of values
- time complexity | worst O(n log n)
- space complexity | O(n)