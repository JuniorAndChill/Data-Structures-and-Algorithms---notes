# C language practice

## 1 
Write a program that uses recursion to display all the odd positive integers, in descending order, from n to 1.

```#include <stdio.h>

int main() {
    int n = 0;
    int end = 0;
    printf("Enter start and stop: ");
    scanf("%d %d", &n,&end);
    
    for(int i = n; i >= end;i--)
    {
        if(i % 2 != 0){
            printf("%d, ",i);
        }
    }
    return 0;
}```


## 2
The Lucas numbers are defined by:
	L~0~ = 2, L~1~ = 1
	
	for n>1, L~n~ = L~n-1~ + L~n-2~
Write a recursive function that computes the nth Lucas number

```#include <stdio.h>

long long lucas(int n)
{
    if(n < 0){
        return -1;
    }
    if(n == 0){
        return 2;
    }
    
    long long a = 2, b = 1, c;
    
    for (int i = 2; i <= n; i++)
    {
        c = a + b;
        a = b;
        b = c;
    }
    return b;
}

int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    
    //Lucas number is "that many numbers in the sequence" identifier. 3th is 4 because it's the 3rd number in the sequence after 2
    printf("The %dth Lucas number is: %lld\n", n, lucas(n));
    return 0;
}```

## 3
The number of combinations of n elements into k elements, C (n,k), is the number of subsets with k elements that can be formed from a set with n elements, where n and k are non-negative numbers such that n >= k. C (n,k) is also known as the number of ways of choosing k elements from n indistinguishable elements. A recursive definition of it can be made as follows: * (base case) c (n,n) = 1 for any n >= 0
	 * (base case) c (n,0) = 1 for any n >= 0
	 * (recursion) c (n,k) = (n-1,k-1) + c (n-1, k) for 0 < k < n
Use the previous definition to write a function that recursively computes all c (n,k) for any 0 <= k <= n and non-negative integers

```#include <stdio.h>

//compute the number of combos of n elements taken k at a time
int combinations(int n, int k){
    //Base Cases
    if(k == 0 || k == n){
        return 1; //finished
    }
    //Error handling: invalid input
    if(k > n){
        return 0;
    }
    //recursion
    return combinations(n - 1, k - 1) + combinations(n - 1, k);
}

//Driver code
int main() {
    int n = 5;
    int k = 2;
    
    printf("C(%d, %d) = %d\n", n, k, combinations(n, k));
    
    n = 4;
    k = 3;
    
    printf("C(%d, %d) = %d\n", n, k, combinations(n, k));
    
    return 0;
}```

## 4
A palindrome is a string that can be read the same way from left to right or from right to left. Given a nonempty string w of size N, check if it is a palindrome of not.

For example, the string w="hannah" is a palindrome, but w="haha" is not a palindrome. Strings with only one character are considered palindromes, thus w="o" is a palindrome

Write a recursive function that checks if a given string is a palindrome. Assume that the chars of he string are indexed starting at 0.

```#include <stdio.h>
#include <string.h>

//compute the number of combos of n elements taken k at a time
int isPalindrome(char str[], int start, int end){
    //Base case; the ends meet up
    if(start >= end){
        return 1; //it is
    }
    //Base case; failure
    if(str[start] != str [end]){
        return 0; //it is not
    }
    //recursion
    return isPalindrome(str, start + 1, end - 1);
}
void checkPalindrome(char str[]){
    //get length of word to check
    int len = strlen(str);
    if (len == 0){
        printf("The string is a palindrome.\n");
        return;
    }
    //init recursion call
    if(isPalindrome(str, 0, len - 1)){
        printf("The string \"%s\" is a palindrome.✅\n", str);
    }
    else{
        printf("The string \"%s\" is not a palindrome.❌\n", str);
    }
}

//Driver code
int main() {
    checkPalindrome("car");
    checkPalindrome("hannah");
    checkPalindrome("hello");
    checkPalindrome("a");
    return 0;
}```