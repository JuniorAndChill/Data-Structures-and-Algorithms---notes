# Algs/Data class 10 Sept 2025

## Recursion Topics

- Data structure ; errors

- Benefits

- Types

- applications of recursive algorithms

- steps to implement

- complexity **(Big O)**

- how implemented in programming languages



### Recursion is a technique to solve problems where the case at hand is divided into smaller subtasks similar to the original one

- Use the same module to get more out of it

- First structure required in recursion is the **base case**, the case in which the function will no longer call itself (recurse)


### Calculating the Power of a number using Recursion

- You can use recursion to define a function to compute *x<sup>n</sup>* for any number *x* and non-negative integer *n*

- *last in 1st out*
	- `power(5,3) = 5*power(5,2) -> power(5,2) = 5*power(5,1) -> power(5,1) = 5*power(5,0) -> power(5,0) = 1`


### What is a well-defined recursion?

- well defined recursion is a recursive alg that reaches an end state in a finite time

- identify stop condition 1st definitely is keep



### Data structure

- internal function call stack

- function push

- LIFO

- memory allocation


```
*********
*fact(1)*
*fact(2)*
*fact(3)*
*fact(4)*
*fact(5)*
*********
```


## Stack overflow errors

- A stack overflow is an error that occurs when the stack doesn't have space to store necessary data 

- When a recursive function or a loop doesn't reach a point when it stops, the program has an infinite loop or stack overflow


### Example
```java
// Online Java Compiler
// Stack overflow example

class Main {
    public static void main(String[] args) {
        System.out.println("Stack Overflow");
        recurMethod(4);
    }
    public static void recurMethod(int x){
        recurMethod(x+1);
    }
}
```

### Example 1 fix
```java
// Online Java Compiler
// Stack overflow example

class Main {
    public static void main(String[] args) {
        try {
        System.out.println("Stack Overflow exercise");
        recurMethod(4);
        } catch (StackOverflowError e){
            System.out.println("Stack Overflow FOUND");
        }
    }
    public static void recurMethod(int x){
        recurMethod(x+1);
    }
}
```

### Example 1 complete fix
```java
// Online Java Compiler
// Stack overflow example

class Main {
    public static void main(String[] args) {
        try {
        System.out.println("Stack Overflow exercise");
        recurMethod(4);
        } catch (StackOverflowError e){
            System.out.println("Stack Overflow FOUND");
        }
    }
    public static void recurMethod(int x){
        if (x==16)
            return;
        else {
            recurMethod(x+1);
            System.out.print(x + " ");
        }
    }
}
```


## Benefits of using Recursion

- provides a clean and simple way to write code

- the use of recursion is **not** just a way to simplify algorithms

- divide-and-conquer


## Type - Tail Recursion

- in tail recursion, the **last** command in the function is the recursive call 

- modern compilers create more efficient code when it is used

- the following code makes use of tail recursion


## 1.2 Examples of Recursive Methods

- the factorial function is used in many statistics, combinatorics, and computer science formulas

	- Represents the number of permutations or different ways of ordering a list of elements 



## Computing Factorials with Recursion

- the factorial of a non-negative integer *n*, usually written as *"n!"*, is the product of all positive integers less than *n*

- you can define the factorial of a function as: 
```java
    // java factorial example

    factorial(n):
    if n = 0
        return 1
    else
        return n*factorial (n-1)
```


## Computing the Fibonacci sequence

- the Fibonacci sequence is a set of numbers created in a recursive form 
	* it is common to describe the Fibonacci sequence of *f*


## Direct and indirect recursion

- indirect recursion is when a function calls to itself but in an indirect manner

- direct recursion is when the function calls itself directly


## Computing Squares of Numbers with Direct and indirect recursion

- You can calculate the square of a positive integer *n* using recursion with the help of the formula: `[n² = (n -1)*]`


## 1.4 The Tower of Hanoi

- the Tower of Hanoi is a puzzle where you are given a tower formed by some disks and thre pegs (pegs A, B, and C)
	* When you start, the disks are stacked in increasing order on one peg (peg A)
	* the challenge is to move all the disks from peg A to peg C
	* this is a recursion only solution

* [Tower of Hanoi - Geeks for Geeks reference](https:///www.geeksforgeeks.org/dsa/c-program-for-tower-of-hanoi)



## Implementing recursion - steps

* Step1 - Define base case (exit strategy, stop recursive calls)
* Step2 - Define a recursive case
* Step3 - Ensure the recursion terminates
* Step4 - ...*profit*...


## Backtracking: Finding all subsets


- Backtracking is a technique where solutions are constructed by using smaller solutions

	* it can be done recursively or not
	* more systematic
	* focusing on repeated application to a subset of same operation 


### Backtracking solution

- Consider the case of finding a subset S from X = {2,3,4,8} such that the elements of S add up to 6
	* you start with an empty set that, of course, is not a solution since the sum of the elements is 0 
	*



## Recursion vs iteration

*Recursion*
- terminates when the base case becomes true
- logic is built in terms of smaller problems
- every recursive call needs extra space in the stack memory
- smaller code size

*Iteration*
- terminates when the loop condition becomes false
- logic is built using iterating over something
- every iteration does not require any extra space
- larger code size


## Complexity and memory usage

| Approach | Complexity | Memory Usage |
|--------------------|------------|--------------|
| Iterative approach |  O(n) 	  |  O(1) |
| Recursive Approach |  O(n) 	  |  O(n) |



## Programming languages implementation

### Recursive Hello

* C
```c
//RecursiveHello
// Online C compiler to run C program online
#include <stdio.h>
#include <stdlib.h>

void RecursiveHello(int x){
    if (x > 100)
        return;
    else
        printf("%d Hello Recursion!\n", x);
        RecursiveHello(x+1);
}
int main() {
    RecursiveHello(1);
    //for(int i = 1; i < 101; i++){
        //printf("%d Hello Recursion!\n",i);
    //}
    //printf("Try programiz.pro");  
}
```
* Java
```java
// Recursive Hello Java
// Stack overflow example

class Main {
    public static void main(String[] args) {
        RecursiveHello(1);
    }
    public static void RecursiveHello(int x){
        if (x > 100)
            return;
        else
            System.out.println(x + " Hello Recursion!");
            RecursiveHello(x+1);
        }
}
```
* Python
```py
# Recursive Hello
# Write Python 3 code in this online editor and run it.
def recursiveHello(x):
    if x > 100:
        return
    else:
        print(x, "Hello Recursion")
        return(recursiveHello(x+1))
# main        
num = 1 
recursiveHello(num)
```

### Recursive Factorial

* C
```c
//RecursiveFact
// Online C compiler to run C program online
#include <stdio.h>
#include <stdlib.h>

double fact(double n){
    if (n == 0)
        return 1;
    return n * fact(n-1);
}
int main() {
    double x;
    printf("Enter value: ");
    scanf("%lf", &x);
    printf("Fact of %lf : %lf\n", x,fact(x));
    return 1;
}
```


* Java



* Python


