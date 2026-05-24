# 在 C 中存储整数值和字符值

> 原文:[https://www . geesforgeks . org/c 中整数和字符值的存储/](https://www.geeksforgeeks.org/storage-of-integer-and-character-values-in-c/)

整数和字符变量在程序中经常使用，但是很少有人知道这些值实际上是如何存储在 C 语言中的。
下面是几个例子来理解这一点:

*   Taking a positive integer value as **char:**

    ```cpp
    #include <stdio.h>
    int main()
    {
        char a = 278;
        printf("%d", a);

        return 0;
    }
    ```

    **Output:**

    ```cpp
    22

    ```

    **说明:**首先，编译器在内部将 278 从十进制转换为二进制(100010110)，然后只考虑以二进制表示的那个数字右边的前 8 位，并将这个值存储在变量 a 中，还会对**溢出**给出警告。

*   Taking a negative integer value as **char:**

    ```cpp
    #include <stdio.h>
    int main()
    {
        char a = -129;
        printf("%d", a);

        return 0;
    }
    ```

    **Output:**

    ```cpp
    127

    ```

    **说明:**首先要明白负数是以其正对应的 2 的补码形式存储的。编译器在内部将 129 从十进制数系统转换为二进制数系统(10000001)，然后，所有的 0 将被更改为 1，1 将被更改为 0(即做 1 的补码)(0111110)，1 将通过二进制加法被添加到 1 的补码中，以给出该数(011111111)的 2 的补码。现在，取二进制补码的最右边 8 位，并按原样存储在变量 a 中。它还会对**溢出**发出警告。

**注:**同样的概念用于存储整数变量，不同的是最后取的位数是 16(2 字节)或 32(4 字节)位，因为 int 变量的大小是 2 或 4 字节。