# –>(前往)C/ C++

> 原文:[https://www.geeksforgeeks.org/goes-to-in-c-c/](https://www.geeksforgeeks.org/goes-to-in-c-c/)

**–>**在 [C](https://www.geeksforgeeks.org/c-programming-language/) / [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中被称为**【前往】**，在包括 **GCC** 和 **MSVN** 在内的每一个编译器中都编译精细。该运算符**(–>)**在任何 C/ C++ 标准中都没有描述，因为它不是实际的运算符，而是两个运算符**(–**)和 **( > )** 的混合。

**程序 1:**

下面是程序举例说明的推移'–> '运算符:

## C

```cpp
// C program to illustrate the use of
// goes to (-->) operator
#include <stdio.h>

// Driver Code
int main()
{
    // Initialize a variable x
    int x = 10;

    // x goes to 0
    while (x-- > 0) {
        printf("%d ", x);
    }

    // Print value of x after
    // loop exists
    printf("\n%d ", x);
}
```

## c++

```cpp
// C++ program to illustrate the use
// of goes to (-->) operator
#include <stdio.h>

// Driver Code
int main()
{
    // Initialize a variable x
    int x = 10;

    // x goes to 0
    while (x-- > 0) {
        cout << ' ' << x;
    }

    // Print value of x after
    // loop exists
    cout << "\n"
         << x;
}
```

**输出:**

```cpp
9 8 7 6 5 4 3 2 1 0 
-1

```