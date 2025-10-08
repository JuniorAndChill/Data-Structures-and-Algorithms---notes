# Algs/Data class 3 Sept 2025

## Pointers in C lang

### Pointer example

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    // To define a pointer you just add * before the variable name
    int *iPtr;
    double *dPtr;
    float *fPtr;
    char *cPtr;
    
    int x = 100;
    iPtr = &x; //assign pointer to the value of x
    
    // until assigned, this will spit random garbble.
    printf("value of iPtr: %x\n ", iPtr); //%x is the hex value specifier(or %p for pointer)
    // because x is stored, it spits a hex value address
    printf("value of x: %d, address of x: %x ", x, &x);
    
    //in hex addressing, caps don't matter due to limited ranges
    return 0;
}
```


### Pointers as Values

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int x = 20;
    float y = 1.3f;
    char z = 'p';
    
    //you can set pointers initially 
    int *xPtr = &x;
    float *yPtr = &y;
    char *zPtr = &z;
    
    //make sure to use the correct designators
    printf("value of x: %d\nvalue of y: %f\nvalue of z: %c\n", *xPtr, *yPtr, *zPtr);
    return 0;
}
```


### Pointers: SizeOf

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int x = 20;
    float y = 1.3f;
    char z = 'p';
    
    //you can set pointers initially 
    int *xPtr = &x;
    float *yPtr = &y;
    char *zPtr = &z;
    
    printf("value of x: %d, address of x: %p\n", x,&x);
    
    //we can find the size of pointers or data types
    //make sure to use the correct designators
    printf("size of x: %d\nsize of y: %d\nsize of z: %d\n", sizeof(x), sizeof(y), sizeof(z));
    printf("size of xPtr: %d\nsize of yPtr: %d\nsize of zPtr: %d\n", sizeof(xPtr), sizeof(yPtr), sizeof(zPtr)); //will always be 8 bytes
    return 0;
}
```


### Pointer to pointer

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int var = 10;
    int *intPtr = &var; //dynamicly allocate address in the app
    int **ptrPtr = &intPtr; //needs 2 * to follow previous pointer as well
    
    
    printf("value of var: %d\naddress of var: %p\nvalue of intPtr: %d\naddress of intPtr: %p\nvalue of ptrPtr: %d\naddress of ptrPtr: %p", var, &var, *intPtr, &intPtr, **ptrPtr, &ptrPtr);
    // to read pointer values you need to add * per pointer
    
    return 0;
}
```


### Pointer Arithmatic

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int x = 10;
    int *y = &x;
    printf("value of x: %d\naddress of x: %p\n", x, &x);
    x++;
    printf("value of x after x++: %d\naddress of x: %p\n", x, &x);
    printf("value of y: %d\naddress of y: %p\n", *y, y);
    y++; //this will iterate the address space by 1 int value (4bytes)
    printf("value of y after y++: %d\naddress of y: %p\n", *y, y);
    
    int a = 25;
    int *b = &a;
    printf("value of b: %d\naddress of b: %p\n", *b, b);
    b--;
    printf("value of b after b++: %d\naddress of b: %p\n", *b, b);
    return 0;
}
```


### Pointer Arrays

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int score [] = {80, 90, 100};
    int *ptr;
    
    ptr = score;
    
    for(int i = 0; i < 3; i++){
       printf("%d %d %p",i,score[i],&score[i]);
       printf("| %d %d %p\n",i, *ptr, ptr); //using pointer to display array
       ptr++; //iterate to keep track of elements via address
    }
    
    return 0;
}
```


### Pointer: Function end

```c
#include <stdlib.h>
#include <stdio.h>

void sayHello(){
    printf("Hello Cardinals!\n");
}

//technically a pointer as well
void sumNumbers(int a, int b){
    int c = a + b;
    printf("Sum is %d\n", c);
}

int main() {
    
    //define and print pointer with no values
    printf("address of sayHello: %p\n", &sayHello);
    void (*helloPtr)() = sayHello; //use void to point to voids
    printf("address of helloPtr: %p\n", &helloPtr);
    sayHello(); //calling method to print
    (*helloPtr)(); //using pointer to print
    helloPtr(); //calling helloPtr as method to print
    printf("\n");
    
    //define and print pointer w/passing values
    void (*sumPtr)(int, int) = sumNumbers;
    (*sumPtr)(4,5); //you can use pointer to run method
    sumPtr(3,2); //functions are also pointer so you can use it either way
    
    return 0;
}
```


### Pointer: Function with parameter and return value

```c
#include <stdio.h>
#include <stdlib.h>

int AddNumbers(int a, int b){
    return a + b;
}

int main() {
    //we can pass return values directly into our pointers and here are 3 ways to do the same thing
    int (*AddPtr) (int, int) = AddNumbers;
    printf("sum: %d\n", AddNumbers(4,5));
    printf("sum: %d\n", (*AddPtr)(6,7));
    printf("sum: %d\n", AddPtr(3,4));
    return 0;
}
```


### Pointer: As Function parameter

```c
#include <stdio.h>
#include <stdlib.h>

int Add(int x, int y){
    return x + y;
}

int Sub(int x, int y){
    return x - y;
}

int Mult(int x, int y){
    return x * y;
}

// supply 3 values
int DoMath(int(*oper)(int, int), int x, int y){
    return (*oper)(x, y);
}

int main() {
    //we can pass return values directly into our pointers and here are 2 ways to do the same thing
    int apple = 100, banana = 87;
    printf("sum: %d\n", Add(apple, banana));
    printf("sum: %d\n", DoMath(Add, apple, banana));
    printf("difference: %d\n", Sub(apple, banana));
    printf("difference: %d\n", DoMath(Sub, apple, banana));
    printf("product: %d\n", Mult(apple, banana));
    printf("product: %d\n", DoMath(Mult, apple, banana));
    return 0;
}
```