# C++和Java中的Foreach

> 原文: [https://www.geeksforgeeks.org/g-fact-40-foreach-in-c-and-java/](https://www.geeksforgeeks.org/g-fact-40-foreach-in-c-and-java/)

[Foreach循环](https://www.geeksforgeeks.org/for-each-loop-in-java/)用于快速访问数组的元素，无需执行初始化、测试和递增/递减。foreach循环的工作是为每个元素做一些事情，而不是做n次。

C语言中没有foreach循环，但是C++和Java都支持foreach类型的循环。在C++中，它是在C++11中引入的，在JDK 1.5.0中是在Java中引入的。

foreach循环使用的关键字在C++和Java中都是`for`。

## C++程序

```cpp
// C++ program to demonstrate use of foreach
#include <iostream>
using namespace std;

int main()
{
    int arr[] = { 10, 20, 30, 40 };

    // Printing elements of an array using
    // foreach loop
    for (int x : arr)
        cout << x << endl;
}
```

**Output:**

```cpp

```

## Java程序

```java
// Java program to demonstrate use of foreach
public class Main {
    public static void main(String[] args)
    {
        // Declaring 1-D array with size 4
        int arr[] = { 10, 20, 30, 40 };

        // Printing elements of an array using
        // foreach loop
        for (int x : arr)
            System.out.println(x);
    }
}
```

**Output:**

```java

```

Foreach循环的优点:
1. 使代码更易读。
2. 消除编程错误的可能性。

本文由Rahul Aggarwal供稿。如果你喜欢GeeksforGeeks并想投稿，你也可以写一篇文章并把你的文章邮寄到contribute@geeksforgeeks.org。看到你的文章出现在GeeksforGeeks主页上，帮助其他Geeks。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论。