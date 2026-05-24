# 检查给定括号表达式是否平衡

> 原文: [https://www.geeksforgeeks.org/check-if-given-parentheses-expression-is-balanced-or-not/](https://www.geeksforgeeks.org/check-if-given-parentheses-expression-is-balanced-or-not/)

给定一个长度为 `N` 的字符串，仅由字符 `(` 和 `)` 组成，任务是检查其括号是否平衡。

**示例:**

> **输入:** `str = "((()))()"`
> **输出:** 平衡
>
> **输入:** `str = "()((())"`
> **输出:** 不平衡

**思路:**

*   声明一个 `flag` 变量，表示表达式是否平衡。
*   将 `flag` 变量初始化为真，`count` 变量为 0。
*   遍历给定的表达式：
    1.  如果我们遇到一个左括号 `(`，将 `count` 增加 1。
    2.  如果我们遇到右括号 `)`，将 `count` 减少 1。
    3.  如果 `count` 在任一点变为负数，则表示表达式不平衡，因此将 `flag` 标记为假，并从循环中断开。
*   遍历表达式后，如果 `count` 不等于 0，表示表达式不平衡，因此将 `flag` 标记为 false。
*   最后，如果 `flag` 为真，则表示平衡，否则表示不平衡。

下面是上述方法的实现：

## C

```c
// C program of the above approach
#include <stdbool.h>
#include <stdio.h>

// Function to check if
// parentheses are balanced
bool isBalanced(char exp[])
{
    // Initialising Variables
    bool flag = true;
    int count = 0;

    // Traversing the Expression
    for (int i = 0; exp[i] != '\0'; i++) {

        if (exp[i] == '(') {
            count++;
        }
        else {
            // It is a closing parenthesis
            count--;
        }
        if (count < 0) {
            // This means there are
            // more Closing parenthesis
            // than opening ones
            flag = false;
            break;
        }
    }

    // If count is not zero,
    // It means there are more
    // opening parenthesis
    if (count != 0) {
        flag = false;
    }

    return flag;
}

// Driver code
int main()
{
    char exp1[] = "((()))()()";

    if (isBalanced(exp1))
        printf("Balanced \n");
    else
        printf("Not Balanced \n");

    char exp2[] = "())((())";

    if (isBalanced(exp2))
        printf("Balanced \n");
    else
        printf("Not Balanced \n");

    return 0;
}
```

## C++

```cpp
// C++ program for the above approach.

#include <bits/stdc++.h>
using namespace std;

// Function to check
// if parentheses are balanced
bool isBalanced(string exp)
{

    // Initialising Variables
    bool flag = true;
    int count = 0;

    // Traversing the Expression
    for (int i = 0; i < exp.length(); i++) {

        if (exp[i] == '(') {
            count++;
        }
        else {

            // It is a closing parenthesis
            count--;
        }
        if (count < 0) {

            // This means there are
            // more Closing parenthesis
            // than opening ones
            flag = false;
            break;
        }
    }

    // If count is not zero,
    // It means there are
    // more opening parenthesis
    if (count != 0) {
        flag = false;
    }

    return flag;
}

// Driver code
int main()
{
    string exp1 = "((()))()()";

    if (isBalanced(exp1))
        cout << "Balanced \n";
    else
        cout << "Not Balanced \n";

    string exp2 = "())((())";

    if (isBalanced(exp2))
        cout << "Balanced \n";
    else
        cout << "Not Balanced \n";

    return 0;
}
```

## Java

```java
// Java program for the above approach.
class GFG{

// Function to check
// if parentheses are balanced
public static boolean isBalanced(String exp)
{

    // Initialising variables
    boolean flag = true;
    int count = 0;

    // Traversing the expression
    for(int i = 0; i < exp.length(); i++)
    {
        if (exp.charAt(i) == '(')
        {
            count++;
        }
        else
        {

            // It is a closing parenthesis
            count--;
        }
        if (count < 0)
        {

            // This means there are
            // more Closing parenthesis
            // than opening ones
            flag = false;
            break;
        }
    }

    // If count is not zero,
    // It means there are
    // more opening parenthesis
    if (count != 0)
    {
        flag = false;
    }
    return flag;
}

// Driver code
public static void main(String[] args)
{
    String exp1 = "((()))()()";

    if (isBalanced(exp1))
        System.out.println("Balanced");
    else
        System.out.println("Not Balanced");

    String exp2 = "())((())";

    if (isBalanced(exp2))
        System.out.println("Balanced");
    else
        System.out.println("Not Balanced");
}
}

// This code is contributed by divyeshrabadiya07
```

## Python 3

```python
# Python3 program for the above approach

# Function to check if
# parenthesis are balanced
def isBalanced(exp):

    # Initialising Variables
    flag = True
    count = 0

    # Traversing the Expression
    for i in range(len(exp)):
        if (exp[i] == '('):
            count += 1
        else:

            # It is a closing parenthesis
            count -= 1

        if (count < 0):

            # This means there are
            # more closing parenthesis
            # than opening
            flag = False
            break

    # If count is not zero ,
    # it means there are more
    # opening parenthesis
    if (count != 0):
        flag = False

    return flag

# Driver code
if __name__ == '__main__':

    exp1 = "((()))()()"

    if (isBalanced(exp1)):
        print("Balanced")
    else:
        print("Not Balanced")

    exp2 = "())((())"

    if (isBalanced(exp2)):
        print("Balanced")
    else:
        print("Not Balanced")

# This code is contributed by himanshu77
```

## C#

```csharp
// C# program for the above approach.
using System;

class GFG{

// Function to check
// if parentheses are balanced
public static bool isBalanced(String exp)
{

    // Initialising variables
    bool flag = true;
    int count = 0;

    // Traversing the expression
    for(int i = 0; i < exp.Length; i++)
    {
        if (exp[i] == '(')
        {
            count++;
        }
        else
        {

            // It is a closing parenthesis
            count--;
        }
        if (count < 0)
        {

            // This means there are
            // more Closing parenthesis
            // than opening ones
            flag = false;
            break;
        }
    }

    // If count is not zero,
    // It means there are
    // more opening parenthesis
    if (count != 0)
    {
        flag = false;
    }
    return flag;
}

// Driver code
public static void Main(String[] args)
{
    String exp1 = "((()))()()";

    if (isBalanced(exp1))
        Console.WriteLine("Balanced");
    else
        Console.WriteLine("Not Balanced");

    String exp2 = "())((())";

    if (isBalanced(exp2))
        Console.WriteLine("Balanced");
    else
        Console.WriteLine("Not Balanced");
}
}

// This code is contributed by Amit Katiyar
```

**输出:**

```
Balanced
Not Balanced
```

**时间复杂度:** `O(N)`
**辅助空间:** `O(1)`