# Java system . exit(0)vs c++ return 0

> 原文:[https://www . geesforgeks . org/Java-system-exit 0-vs-c-return-0/](https://www.geeksforgeeks.org/java-system-exit0-vs-c-return-0/)

Java 和 C++ 是具有不同应用和设计目标的语言。C++ 是过程编程语言 C 的扩展，Java 依赖于 Java 虚拟机来实现安全性和高度可移植性。这导致他们有许多不同。在本文中，我们将看到 *C++ 返回 0* 和 *Java System.exit(0)* 的区别。在讨论这些差异之前，让我们先了解它们各自的真正含义。

### C++ 返回 0

*   在标准 C++ 中，建议创建一个带有返回类型的 *main()* 函数。
*   所以， *main()* 函数必须返回一个整数值，这个整数值通常是要传递回操作系统的值。

在 *stdlib.h* 中，宏*退出 _ 成功*和*退出 _ 失败*是这样定义的:

```cpp
#define EXIT_SUCCESS    0
#define EXIT_FAILURE    1

```

*   **返回 0–>**成功终止。
*   **返回 1** 或任何其他**非零**值–>不成功终止。
*   返回不同的值，如**返回 1** 或**返回-1** 或任何其他**非零**值意味着程序返回错误。

## C++

```cpp
#include <iostream>

using namespace std;

int main()
{
    int num1, num2;
    cin >> num1 >> num2;
    cout << num1 + num2;

    return 0;
}
```

```cpp
Input:
54
4

Output:
58

```

### Java System.exit(0)

首先要考虑的是**Java 中的主函数有一个返回类型 *void* 。**

*   **在 Java 中，您不能返回退出代码，因为它是一个 void 函数。所以，如果要明确指定退出代码，就必须使用 *System.exit()* 方法。**
*   ***java.lang.System.exit()* 方法通过终止运行 java 虚拟机退出当前程序。**

****Java . lang . system . exit()方法的声明:****

```cpp
public static void exit(int status)
**exit(0) -->**successful termination.
**exit(1)** or **exit(-1)** or any other non-zero value –-> unsuccessful termination. 
```

## **Java 语言(一种计算机语言，尤用于创建网站)**

```cpp
import java.io.*;

class GFG {
    public static void main (String[] args) {
        System.out.println("GeeksForGeeks");
    }
}
```

```cpp
**Output:**
GeeksforGeeks
```

****注:**两个*返回 0* 和*系统.退出(0)* 的工作与*主()*功能返回类型的区别相同。**

****下表描述了差异:****

<figure class="table">

| -你好。不，不 | c++ 返回 0 | Java 系统。出口(0) |
| --- | --- | --- |
| 1。 | The main () function in c++ has a return type. Therefore, every main method in C++ should return a value. | The main () method in Java belongs to void return type. Therefore, the main method should not return a value. |
| 2。 | In C++ programs, the return 0 statement is optional: the compiler will automatically add a return 0 implicitly in the program. | In Java, there are no special requirements for calling System.exit(0) or adding explicitly. |
| 3。 | Is a keyword used to return a value, so no declaration is required. It only needs to return keywords with values or variables. | 申报为 java.lang.System.exit()方法:*公静虚空退出(int 状态)* |
| 4。 | Generally, return 0 is used to return the exit code to the operating system. | If you want to explicitly specify the exit code of the operating system, you must use System.exit (). |
| 5。 | It is considered a good practice to use return 0 in C++ programs. | Avoid using System.exit(0) in practice, because our main () method has a void return type. |

</figure>