# 在 C

中将数组的所有成员初始化为相同值的不同方法

> 原文:[https://www . geeksforgeeks . org/不同的初始化方法将数组的所有成员初始化为 c 中的相同值/](https://www.geeksforgeeks.org/different-ways-to-initialize-all-members-of-an-array-to-the-same-value-in-c/)

数组是保存固定数量的相同类型值的数据集合。例如:如果要存储 100 个学生的分数，可以为其创建一个数组。

```cpp
int num[100];

```

**如何用 C 语言声明数组？**

```cpp
Data_type  array_name[size_of_array];

```

例如，

```cpp
float num[10];

```

以下是将数组的所有元素初始化为相同值的一些不同方法:

1.  **Initializer List**: To initialize an array in C with the same value, the naive way is to provide an initializer list. We use this with small arrays.

    ```cpp
    int num[5] = {1, 1, 1, 1, 1};

    ```

    这将在所有索引处用值 1 初始化 num 数组。
    我们也可以忽略数组的大小:

    ```cpp
    int num[ ] = {1, 1, 1, 1, 1}

    ```

    如果我们提供空的初始化列表或者只是在初始化列表中指定 0，数组将被初始化为 0。

    ```cpp
    int num[5] =  { };                // num = [0, 0, 0, 0, 0]
    int num[5] =  { 0 };             // num = [0, 0, 0, 0, 0]

    ```

2.  **Designated Initializer**: This initializer is used when we want to initialize a range with the same value. This is used only with GCC compilers.
    [ first . . . last ] = value;

    ```cpp
    int num[5]={ [0 . . . 4 ] = 3 };               // num = { 3, 3, 3, 3, 3}

    ```

    我们也可以忽略数组的大小:

    ```cpp
    int num[  ]={ [0 . . . 4 ] = 3 };               // num = { 3, 3, 3, 3, 3}

    ```

3.  **宏**:初始化一个相同值的巨大数组，我们可以使用宏。

    ```cpp
    #include<stdio.h>

    #define x1 1
    #define x2 x1, x1
    #define x4 x2, x2
    #define x8 x4, x4
    #define x16 x8, x8
    #define x32 x16, x16

    int main(void)
    {
    // array declaration
    int num[] = { x32, x8, x4, x1};
    int size = sizeof(num)/ sizeof(int);    // 32+8+4+1= 45

    printf("The size of the array is %d\n", size);
    printf("The value of element in the array at index 5 is %d ", 
                                        num[4]);

    return 0;

    }
    ```

    **输出:**

    ```cpp
    The size of the array is 45
    The value of element in the array at index 5 is 1

    ```

4.  **使用 for 循环**:我们也可以使用 For 循环来初始化一个具有相同值的数组。

    ```cpp
    #include<stdio.h>

    int main(void)
    {
        int size = 6;
        int val = 1;

        // array declaration
        int arr[size];
        int i;

        // initializing array elements
        for (i = 0; i < size ; i++){
            arr[i] = val;
        }

         // print array
         printf("The array is:");
         for (i = 0; i < size ; i++){
             printf("%d ", arr[i]);
        }

        return 0;
    }
    ```

    **输出:**

    ```cpp
    The array is:1 1 1 1 1 1

    ```