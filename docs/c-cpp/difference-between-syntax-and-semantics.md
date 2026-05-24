# 句法和语义的区别

> 原文:[https://www . geesforgeks . org/语法和语义差异/](https://www.geeksforgeeks.org/difference-between-syntax-and-semantics/)

**<u>语法:</u>**

*   它是指用像 [C](https://www.geeksforgeeks.org/c-programming-language/) / [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 这样的编程语言编写任何语句的规则和规定。
*   它与陈述的意思没有任何关系。
*   如果一个语句遵循所有的规则，那么它在语法上是有效的。
*   与语言的语法和[结构](https://www.geeksforgeeks.org/structures-c/)有关。

**<u>语义:</u>**

*   它指的是编程语言中与语句相关联的含义。
*   一切都是关于语句的含义，它能很容易地解释程序。
*   错误在[运行时](https://www.geeksforgeeks.org/runtime-errors/)处理。

**程序 1:**
下面是演示语义错误的代码:

## C++

```cpp
// C++ program to demonstrate semantic error

#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Return statement before cout
    return 0;

    // Print the value
    cout << "GFG!";
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to demonstrate semantic error
import java.util.*;
class GFG
{

// Driver Code
public static void main(String[] args)
{

    // exit() statement before cout
   System.exit(0);

    // Print the value
    System.out.print("GFG!");
}
}

// This code is contributed by aashish1995
```

## 蟒蛇 3

```cpp
# Python program to demonstrate semantic error
import sys

# Driver Code
if __name__ == '__main__':

    # exit() statement before cout
    sys.exit(0);

    # Print the value
    print("GFG!");

# This code is contributed by gauravrajput1
```

## C#

```cpp
// C# program to demonstrate semantic error
using System;

class GFG
{

// Driver Code
public static void Main(String[] args)
{

    // exit() statement before cout
    Environment.Exit(0);

    // Print the value
    Console.Write("GFG!");
}
}

// This code is contributed by gauravrajput1
```

**Output:**