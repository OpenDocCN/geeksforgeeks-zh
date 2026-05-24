# 不要在 C

中使用数组参数的大小

> 原文:[https://www . geeksforgeeks . org/using-siziof-operator-with-array-parameters-in-c/](https://www.geeksforgeeks.org/using-sizof-operator-with-array-paratmeters-in-c/)

直接使用的**大小来查找数组的大小会导致代码出错，因为数组参数被视为指针。考虑下面的程序。**

 **## C

```cpp
// C Program to demonstrate incorrect usage of sizeof() for
// arrays
#include <stdio.h>

void fun(int arr[])
{
    int i;

    // sizeof should not be used here to get number
    //  of elements in array
    int arr_size = sizeof(arr) / sizeof(arr[0]);

    for (i = 0; i < arr_size; i++) {
        arr[i] = i;
    }
    // executed only once
}

// Driver Code
int main()
{
    int i;
    int arr[4] = { 0, 0, 0, 0 };
    fun(arr);

    // use of sizeof is fine here
    for (i = 0; i < sizeof(arr) / sizeof(arr[0]); i++)
        printf(" %d ", arr[i]);

    getchar();
    return 0;
}
```** 

**解释:**当 fun()函数接收到数组参数‘arr[]’并试图使用 **sizeof 运算符找出 arr[]中的元素数量时，该代码会生成一个错误。**

在 C 语言中，数组参数被视为指针(详见 [**本**](https://www.geeksforgeeks.org/why-c-treats-array-parameters-as-pointers/) )。因此，表达式**sizeof(arr)/sizeof(arr[0])**变为 **sizeof(int *)/sizeof(int)** ，结果为 1(int 和 int *的大小为 4)，并且 for 循环内部 fun()只执行一次，与数组的大小无关。因此，在这种情况下，不应使用**大小的**来获取多个元素。

### 解决方案:

**1)使用单独的参数:**用于数组大小或长度的单独的数据类型参数 **size_t** 应该传递给 fun()。 **size_t** 是至少 16 位的无符号整数类型。所以**修正程序为:**

## C

```cpp
// C Program to demonstrate correct usage of sizeof() for
// arrays
#include <stdio.h>

void fun(int arr[], size_t arr_size)
{
    int i;
    for (i = 0; i < arr_size; i++) {
        arr[i] = i;
    }
}

// Driver Code
int main()
{
    int i;
    int arr[] = { 0, 0, 0, 0 };
    size_t n = sizeof(arr) / sizeof(arr[0]);
    fun(arr, n);

    printf("The size of the array is: %ld", n);
    printf("\nThe elements are:\n");
    for (i = 0; i < n; i++)
        printf(" %d ", arr[i]);

    getchar();
    return 0;
}
```

**Output**

```cpp
The size of the array is: 4
The elements are:
 0  1  2  3 
```

**2)** **使用宏:**我们甚至可以定义**宏**使用**#定义**来查找数组的大小，如下图所示，

## C

```cpp
// C Program to demonstrate usage of macros to find the size
// of arrays
#include <stdio.h>

#define SIZEOF(arr) sizeof(arr) / sizeof(*arr)

void fun(int arr[], size_t arr_size)
{
    int i;
    for (i = 0; i < arr_size; i++) {
        arr[i] = i;
    }
}

// Driver Code
int main()
{
    int i;
    int arr[] = { 0, 0, 0, 0, 0 };
    size_t n = SIZEOF(arr);
    fun(arr, n);

    printf("The size of the array is: %ld", n);
    printf("\nThe elements are:\n");
    for (i = 0; i < n; i++)
        printf(" %d ", arr[i]);

    return 0;
}
```

**输出**

```cpp
The size of the array is: 5
The elements are:
 0  1  2  3  4 
```

T19】

**3)使用指针算法:**我们可以使用**(&arr)【1】–arr**来找到数组的大小。这里， **arr** 指向数组的第一个元素，类型为 **int*。**和， **& arr** 的类型为 **int*[n]** ，指向整个数组。因此，它们的差异相当于数组的大小。

## C

```cpp
// C Program to demonstrate usage of pointer arithmetic to
// find the size of arrays
#include <stdio.h>

void fun(int arr[], size_t arr_size)
{
    int i;
    for (i = 0; i < arr_size; i++) {
        arr[i] = i;
    }
}

// Driver Code
int main()
{
    int i;
    int arr[] = { 0, 0, 0, 0, 0 };
    size_t n = (&arr)[1] - arr;
    fun(arr, n);

    printf("The size of the array is: %ld", n);
    printf("\nThe elements are:\n");
    for (i = 0; i < n; i++)
        printf(" %d ", arr[i]);

    return 0;
}
```

**输出**

```cpp
The size of the array is: 5
The elements are:
 0  1  2  3  4 
```

如果你在上面的文章中发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写评论。