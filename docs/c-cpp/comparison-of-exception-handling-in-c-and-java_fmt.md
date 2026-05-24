# C++ 和 Java 异常处理的比较

> 原文: [https://www.geeksforgeeks.org/comparison-of-exception-handling-in-c-and-java/](https://www.geeksforgeeks.org/comparison-of-exception-handling-in-c-and-java/)

两种语言都使用到 `try`、`catch`、`throw` 关键词进行异常处理，它们的含义在两种语言中也是一样的。

**以下是 Java 和 C++ 异常处理的区别:**

| Java | C++ |
| --- | --- |
| 只有可抛出的对象才能作为异常抛出。 | 所有类型都可以作为异常抛出。 |
| 我们可以通过捕获异常对象来捕获所有种类的异常。因为通常，我们不会捕获除异常之外的任何可抛出物。 | 有一种特殊的捕获叫做“catch all”，可以捕获所有种类的异常。 |
| 有一个特殊的块叫做 `finally`，它总是在 `try-catch` 块之后最后执行。 | C++ 中没有这样的块。 |
| 有两种异常：已检查（checked）和未检查（unchecked）。 | 所有异常都是未检查的。 |
| 一个特殊的关键字 `throws` 用来列出函数可能抛出的异常。 | 关键字 `throw` 用来列出函数可能抛出的异常。 |
| 在 Java 中查找和处理异常很容易。 | 在 C++ 中查找和处理异常相当困难。 |

**以上几点已经在下面详细讨论:**

## 1) 可抛出的类型

在 C++ 中，所有类型（包括原语和指针）都可以作为异常抛出。但是在 Java 中，只有可抛出对象（`Throwable` 类或其任何子类的实例）可以作为异常抛出。例如，以下类型的代码在 C++ 中有效，但类似的代码在 Java 中无效。

```cpp
// CPP Program to demonstrate all types (including primitive
// and pointer) can be thrown as exception.
#include <iostream>
using namespace std;
int main()
{
    int x = -1;

    // some other stuff
    try {
        // some other stuff
        if (x < 0) {
            throw x;
        }
    }
    catch (int x) {
        cout << "Exception occurred: thrown value is " << x
             << endl;
    }
    getchar();
    return 0;
}
```

**Output**

```cpp
Exception occurred: thrown value is -1
```

## 2) 捕获所有异常

在 C++ 中，有一个特殊的 `catch` 叫做“catch all”，可以捕获各种异常。

```cpp
// CPP Program to demonstrate catch all
#include <iostream>
using namespace std;
int main()
{
    int x = -1;
    char* ptr;

    ptr = new char[256];

    try {

        if (x < 0) {
            throw x;
        }
        if (ptr == NULL) {
            throw " ptr is NULL ";
        }
    }
    catch (...) // catch all
    {
        cout << "Exception occurred: exiting " << endl;
        exit(0);
    }

    getchar();
    return 0;
}
```

**Output**

```cpp
Exception occurred: exiting
```

在 Java 中，出于所有实际目的，我们可以通过捕获 `Exception` 对象来捕获各种异常。因为除了异常（即错误）之外，我们通常不会捕获 `Throwable`。

```java
catch(Exception e){
 …….
}
```

## 3) finally 块

在 Java 中，有一个名为 `finally` 的块，它总是在 `try-catch` 块之后执行。这个区块可以用来做清理工作。C++ 中没有这样的块。

```java
// Java Program to demonstrate creating an exception type
class Test extends Exception {
}

class Main {
    public static void main(String args[])
    {

        try {
            throw new Test();
        }
        catch (Test t) {
            System.out.println("Got the Test Exception");
        }
        finally {
            System.out.println("Inside finally block ");
        }
    }
}
```

**Output**

```java
Got the Test Exception
Inside finally block
```

## 4) 已检查与未检查异常

在 C++ 中，所有异常都是未检查的。在 Java 中，有两种类型的异常——已检查（checked）和未检查（unchecked）。有关已检查与未检查异常的更多详细信息，请参见[本教程](http://tutorials.jenkov.com/java-exception-handling/checked-or-unchecked-exceptions.html)。

## 5) throws 关键字

在 Java 中，一个新的关键字 `throws` 用来列出一个函数可以抛出的异常。在 C++ 中，没有 `throws` 关键字，同样的关键字 `throw` 也用于此目的。

## 6) 异常处理与程序终止

在 C++ 中，如果异常没有被捕获，那么异常处理子系统调用函数 `unexpected()`，异常终止程序或应用程序。如果在我们的 C++ 程序中出现任何异常，那么找到那个特定的异常是非常耗时的，因为在 C++ 中，`unexpected()` 没有告诉我们异常发生在哪个类型和哪一行。有关 `unexpected()` 的更多详情，请参考[本文](https://www.geeksforgeeks.org/customizing-termination-behavior-uncaught-exception-c/#:~:text=The%20exception%20handling%20subsystem%20calls,be%20performed%20during%20process%20termination.)。

但是在 Java 中，如果系统生成的异常没有被捕获，那么 Java 运行时系统（JVM）会将异常对象切换到默认的异常处理程序，该程序基本上打印名称、描述以及异常发生在哪一行。因此，在 Java 中查找和处理异常比在 C++ 语言中更容易。

有关默认异常处理程序的更多详细信息，请参见[本文](https://www.geeksforgeeks.org/exceptions-in-java/)。