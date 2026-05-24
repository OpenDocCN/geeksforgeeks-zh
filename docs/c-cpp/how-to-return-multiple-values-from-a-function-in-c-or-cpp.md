# 如何在 C 或 C++ 中从一个函数返回多个值？

> 原文:[https://www . geesforgeks . org/如何从 c 或-cpp 中的函数返回多个值/](https://www.geeksforgeeks.org/how-to-return-multiple-values-from-a-function-in-c-or-cpp/)

新程序员通常在寻找从一个函数返回多个值的方法。不幸的是，C 和 C++ 不允许直接这样做。但幸运的是，通过一点点巧妙的编程，我们可以轻松实现这一点。

**下面是使用指针从 C:**

1.  A function in returns multiple values.
2.  By using the structure.
3.  By using arrays.

**例子:**考虑一个例子，其中的任务是找到两个不同数字中较大和较小的那个。我们可以编写多个函数。主要的问题是调用多个函数的麻烦，因为我们需要返回多个值，当然，需要键入更多的代码行。

1.  **Return multiple values with pointers:** Pass parameters with addresses and use pointers to change their values. These values become the original parameters.

    ```cpp
    // Modified program using pointers
    #include <stdio.h>

    // add is the short name for address
    void compare(int a, int b, int* add_great, int* add_small)
    {
        if (a > b) {

            // a is stored in the address pointed
            // by the pointer variable *add_great
            *add_great = a;
            *add_small = b;
        }
        else {
            *add_great = b;
            *add_small = a;
        }
    }

    // Driver code
    int main()
    {
        int great, small, x, y;

        printf("Enter two numbers: \n");
        scanf("%d%d", &x, &y);

        // The last two arguments are passed
        // by giving addresses of memory locations
        compare(x, y, &great, &small);
        printf("\nThe greater number is %d and the"
               "smaller number is %d",
               great, small);

        return 0;
    }
    ```

    **Output:**

```cpp
Enter two numbers: 
5 8
The greater number is 8 and the smaller number is 5

```