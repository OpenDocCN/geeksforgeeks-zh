# C 中 0 或 1 变量的隐式初始化

> 原文:[https://www . geesforgeks . org/隐式-变量初始化-0 或-1 in-c/](https://www.geeksforgeeks.org/implicit-initialization-of-variables-with-0-or-1-in-c/)

在 C 编程语言中，变量应该在赋值之前声明。
**例如:**

```cpp
   // declaration of variable a and 
   // initializing it with 0.
   int a = 0;

   // declaring array arr and initializing 
   // all the values of arr as 0.
   int arr[5] = {0}; 

```

然而，变量可以用 0 或 1 赋值，甚至不用声明它们。让我们看一个例子，看看如何做到这一点:

```cpp
#include <stdio.h>
#include <stdlib.h>

// implicit initialization of variables
a, b, arr[3];

// value of i is initialized to 1
int main(i)
{
    printf("a = %d, b = %d\n\n", a, b);

    printf("arr[0] = %d, \narr[1] = %d, \narr[2] = %d,"
                "\n\n", arr[0], arr[1], arr[2]);

    printf("i = %d\n", i);

    return 0;
}
```

**Output:**

```cpp
a = 0, b = 0

arr[0] = 0, 
arr[1] = 0, 
arr[2] = 0, 

i = 1

```

在数组中，如果使用的元素少于指定的数组大小，则剩余的元素将默认设置为 0。
我们再看一个例子来说明这一点。

```cpp
#include <stdio.h>
#include <stdlib.h>

int main()
{
    // size of the array is 5, but only array[0],
    // array[1] and array[2] are initialized
    int arr[5] = { 1, 2, 3 };

    // printing all the elements of the array
    int i;
    for (i = 0; i < 5; i++) {
        printf("arr[%d] = %d\n", i, arr[i]);
    }

    return 0;
}
```

**Output:**

```cpp
arr[0] = 1
arr[1] = 2
arr[2] = 3
arr[3] = 0
arr[4] = 0

```