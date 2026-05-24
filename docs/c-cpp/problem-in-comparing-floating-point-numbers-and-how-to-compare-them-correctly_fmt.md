# 浮点数比较中的问题以及如何正确比较？

> 原文：[https://www.geeksforgeeks.org/problem-in-comparing-floating-point-numbers-and-how-to-compare-them-correctly/](https://www.geeksforgeeks.org/problem-in-comparing-floating-point-numbers-and-how-to-compare-them-correctly/)

在本文中，我们将了解比较浮点数的问题，并讨论比较两个浮点数的正确方法。

## 通常比较浮点数有什么问题？

我们先借助`关系运算符(==)`比较两个浮点数。

**示例：**使用“==”进行比较

### C++

```cpp
// C++ program to compare
// floating point numbers

#include <bits/stdc++.h>
using namespace std;

void compareFloatNum(double a, double b)
{
    if (a == b) {
        cout << "The numbers are equal"
             << endl;
    }
    else {
        cout << "The numbers are not equal"
             << endl;
    }
}

// Driver code
int main()
{
    double a = (0.3 * 3) + 0.1;
    double b = 1;
    compareFloatNum(a, b);
}
```

### Java

```java
// Java program to compare
// floating point numbers
class GFG
{

    static void compareFloatNum(double a, double b)
    {
        if (a == b)
        {
            System.out.print("The numbers are equal" + "\n");
        }
        else
        {
            System.out.print("The numbers are not equal" + "\n");
        }
    }

    // Driver code
    public static void main(String[] args)
    {
        double a = (0.3 * 3) + 0.1;
        double b = 1;
        compareFloatNum(a, b);
    }
}

// This code is contributed by 29AjayKumar
```

### Python

```python
# Python program to compare
# floating point numbers
def compareFloatNum(a, b):
    if (a == b):
        print("The numbers are equal")

    else:
        print("The numbers are not equal")

# Driver code

a = (0.3 * 3) + 0.1
b = 1
compareFloatNum(a, b)

# This code is contributed by mohit kumar 29
```

### C#

```csharp
// C# program to compare
// floating point numbers
using System;

class GFG
{

    static void comparefloatNum(double a, double b)
    {
        if (a == b)
        {
            Console.Write("The numbers are equal" + "\n");
        }
        else
        {
            Console.Write("The numbers are not equal" + "\n");
        }
    }

    // Driver code
    public static void Main(String[] args)
    {
        double a = (0.3 * 3) + 0.1;
        double b = 1;
        comparefloatNum(a, b);
    }
}

// This code is contributed by PrinciRaj1992
```

### JavaScript

```javascript
<script>

function compareFloatNum(a,b)
{
    if (a == b)
        {
            document.write("The numbers are equal" + "<br>");
        }
        else
        {
            document.write("The numbers are not equal" + "<br>");
        }
}

let a = (0.3 * 3) + 0.1;
 let b = 1;
 compareFloatNum(a, b);

// This code is contributed by patel2127

</script>
```

**输出：**

```
The numbers are not equal
```

## 为什么会出现这个问题？

在浮点数的情况下，`关系运算符(==)`不会产生正确的输出，这是由于浮点数舍入时的内部精度错误。
在上面的例子中，我们可以看到使用“==”运算符比较两个浮点数的不准确性。两个数字`a`和`b`相等（如`(0.3 * 3) + 0.1 = 1`），但程序导致不正确的输出。
让我们仔细看看下一个片段中的数字。

### C++

```cpp
// C++ program to compare
// floating point numbers

#include <bits/stdc++.h>
using namespace std;

void printFloatNum(double a, double b)
{
    // To print decimal numbers up to 20 digits
    cout << setprecision(20);

    cout << "a is : " << a << endl;
    cout << "b is : " << b << endl;
}

// Driver code
int main()
{
    double a = (0.3 * 3) + 0.1;
    double b = 1;
    printFloatNum(a, b);
}
```

### Python 3

```python
# Python 3 program to compare
# floating point numbers
def printFloatNum(a,  b):

    # To print decimal numbers up to 20 digits
    print("a is : %.20f" %a)
    print("b is : %.20f" %b)

# Driver code
if __name__ == "__main__":

    a = (0.3 * 3) + 0.1
    b = 1
    printFloatNum(a, b)

    # This code is contributed by ukasp.
```

**输出：**

```
a is : 0.99999999999999988898
b is : 1
```