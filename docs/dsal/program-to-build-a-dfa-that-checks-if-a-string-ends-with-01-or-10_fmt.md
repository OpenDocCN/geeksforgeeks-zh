# 构建DFA的程序：检查字符串是否以“01”或“10”结尾

> 原文：[https://www.geeksforgeeks.org/program-to-build-a-dfa-that-checks-if-a-string-ends-with-01-or-10/](https://www.geeksforgeeks.org/program-to-build-a-dfa-that-checks-if-a-string-ends-with-01-or-10/)

## DFA介绍

[DFA](https://www.geeksforgeeks.org/introduction-of-finite-automata/)或[确定性有限自动机](https://www.geeksforgeeks.org/introduction-of-finite-automata/)是一种有限状态机，如果某个字符串达到最终状态，则接受该字符串（在特定条件下），否则拒绝该字符串。

## 问题描述

给定一个由字符`0`和`1`组成的字符串，检查最后两个字符是`"01"`还是`"10"`，否则拒绝该字符串。无论接受或拒绝，也打印状态图。因为在DFA中，没有内存的概念，所以我们一次只能检查一个字符，从第0个字符开始。该问题的输入设置为`{0，1}`。对于输入集中的每个字符，DFA的每个状态都会重定向到另一个有效状态。

## DFA机器

对于上面的问题表述，我们首先要造一台DFA机。DFA机器类似于具有各种状态和转换的流程图。上述问题对应的DFA机如下所示，`Q3`、`Q4`为最终状态：

![DFA- image](img/ca0ad3b82573152344a53742afbbb06b.png)

## 示例

```
Input: 010101
Output:
State transitions are q0->q1->q3->q4->q3->q4->q3->YES
Explanation : 010101 ends with "01".

Input: 0100
Output:
State transitions are q0->q1->q3->q4->q1->NO
Explanation : 0100 ends with "00", which is not equal to any of "01" or "10".
```

## 算法

> 1.  定义构建状态图所需的最少状态数。使用函数来定义各种状态。
> 2.  列出所有有效的转换。对于每个有效符号，每个状态都必须有一个转换。
> 3.  通过应用基本条件定义最终状态。
> 4.  使用状态函数调用定义所有状态转换。
> 5.  定义字符串结束时的返回条件。

对于给定的DFA机器：

> 1.  `Q0`、`Q1`、`Q2`、`Q3`和`Q4`被定义为状态数。
> 2.  `0`和`1`是有效符号。每个状态都有`0`和`1`之间的转换。
> 3.  `Q3`和`Q4`被定义为最终状态。
> 4.  假设在状态`Q0`中，如果输入`0`，则调用函数`Q1`。如果输入`1`，则调用函数`Q2`。
> 5.  如果程序到达字符串末尾，将根据状态输出结果，程序结束。

## 实现

### C++

```cpp
// CPP Program to DFA that accepts string ending
// with 01 or 10.

#include <bits/stdc++.h>
using namespace std;

// Various states of DFA machine are defined
// using functions.
void q1(string, int);
void q2(string, int);
void q3(string, int);
void q4(string, int);

// End position is checked using the string
// length value.
// q0 is the starting state.
// q1 and q2 are intermediate states.
// q3 and q4 are final states.
void q1(string s, int i)
{
    cout << "q1->";

    if (i == s.length()) {
        cout << "NO \n";
        return;
    }

    // state transitions
    // 0 takes to q1, 1 takes to q3
    if (s[i] == '0')
        q1(s, i + 1);
    else
        q3(s, i + 1);
}

void q2(string s, int i)
{
    cout << "q2->";
    if (i == s.length()) {
        cout << "NO \n";
        return;
    }

    // state transitions
    // 0 takes to q4, 1 takes to q2
    if (s[i] == '0')
        q4(s, i + 1);
    else
        q2(s, i + 1);
}

void q3(string s, int i)
{
    cout << "q3->";
    if (i == s.length()) {
        cout << "YES \n";
        return;
    }

    // state transitions
    // 0 takes to q4, 1 takes to q2
    if (s[i] == '0')
        q4(s, i + 1);
    else
        q2(s, i + 1);
}

void q4(string s, int i)
{
    cout << "q4->";
    if (i == s.length()) {
        cout << "YES \n";
        return;
    }

    // state transitions
    // 0 takes to q1, 1 takes to q3
    if (s[i] == '0')
        q1(s, i + 1);
    else
        q3(s, i + 1);
}

void q0(string s, int i)
{
    cout << "q0->";
    if (i == s.length()) {
        cout << "NO \n";
        return;
    }

    // state transitions
    // 0 takes to q1, 1 takes to q2
    if (s[i] == '0')
        q1(s, i + 1);
    else
        q2(s, i + 1);
}

// Driver Code
int main()
{
    string s = "010101";
    // all state transitions are printed.
    // if string is accpetable, YES is printed.
    // else NO is printed
    cout << "State transitions are ";
    q0(s, 0);
}
```

### Java实现

```java
// Java Program to DFA that accepts string ending
// with 01 or 10.
class GFG
{

    // End position is checked using the string
    // length value.
    // q0 is the starting state.
    // q1 and q2 are intermediate states.
    // q3 and q4 are final states.
    static void q1(String s, int i)
    {
        System.out.print("q1->");
        if (i == s.length())
        {
            System.out.println("NO");
            return;
        }

        // state transitions
        // 0 takes to q1, 1 takes to q3
        if (s.charAt(i) == '0')
            q1(s, i + 1);
        else
            q3(s, i + 1);
    }

    static void q2(String s, int i)
    {
        System.out.print("q2->");
        if (i == s.length())
        {
            System.out.println("NO ");
            return;
        }

        // state transitions
        // 0 takes to q4, 1 takes to q2
        if (s.charAt(i) == '0')
            q4(s, i + 1);
        else
            q2(s, i + 1);
    }

    static void q3(String s, int i)
    {
        System.out.print("q3->");
        if (i == s.length())
        {
            System.out.println("YES");
            return;
        }

        // state transitions
        // 0 takes to q4, 1 takes to q2
        if (s.charAt(i) == '0')
            q4(s, i + 1);
        else
            q2(s, i + 1);
    }

    static void q4(String s, int i)
    {
        System.out.print("q4->");
        if (i == s.length())
        {
            System.out.println("YES");
            return;
        }

        // state transitions
        // 0 takes to q1, 1 takes to q3
        if (s.charAt(i) == '0')
            q1(s, i + 1);
        else
            q3(s, i + 1);
    }

    static void q0(String s, int i)
    {
        System.out.print("q0->");
        if (i == s.length())
        {
            System.out.println("NO");
            return;
        }

        // state transitions
        // 0 takes to q1, 1 takes to q2
        if (s.charAt(i) == '0')
            q1(s, i + 1);
        else
            q2(s, i + 1);
    }

    // Driver Code
    public static void main (String[] args)
    {
        String s = "010101";

        // all state transitions are printed.
        // if string is accpetable, YES is printed.
        // else NO is printed
        System.out.print("State transitions are ");
        q0(s, 0);
    }
}

// This code is contributed by AnkitRai01
```

## 蟒蛇 3

```python
# Python3 Program to DFA that accepts string ending
# with 01 or 10.

# End position is checked using the string
# length value.
# `q0` is the starting state.
# `q1` and `q2` are intermediate states.
# `q3` and `q4` are final states.
def q1(s, i) :

    print("q1->", end="");

    if (i == len(s)) :
        print("NO");
        return;

    # state transitions
    # 0 takes to `q1`, 1 takes to `q3`
    if (s[i] == '0') :
        q1(s, i + 1);
    else :
        q3(s, i + 1);

def q2(s, i) :

    print("q2->", end = "");
    if (i == len(s)) :
        print("NO");
        return;

    # state transitions
    # 0 takes to `q4`, 1 takes to `q2`
    if (s[i] == '0') :
        q4(s, i + 1);
    else :
        q2(s, i + 1);

def q3(s, i) :

    print("q3->", end = "");
    if (i == len(s)) :
        print("YES");
        return;

    # state transitions
    # 0 takes to `q4`, 1 takes to `q2`
    if (s[i] == '0') :
        q4(s, i + 1);
    else :
        q2(s, i + 1);

def q4(s, i) :

    print("q4->", end = "");
    if (i == len(s)) :
        print("YES");
        return;

    # state transitions
    # 0 takes to `q1`, 1 takes to `q3`
    if (s[i] == '0') :
        q1(s, i + 1);
    else :
        q3(s, i + 1);

def q0( s, i) :

    print("q0->", end = "");
    if (i == len(s)) :
        print("NO");
        return;

    # state transitions
    # 0 takes to `q1`, 1 takes to `q2`
    if (s[i] == '0') :
        q1(s, i + 1);
    else :
        q2(s, i + 1);

# Driver Code
if __name__ == "__main__" :
    s = "010101";

    # all state transitions are printed.
    # if string is accpetable, YES is printed.
    # else NO is printed
    print("State transitions are", end = " ");
    q0(s, 0);

# This code is contributed by AnkitRai01
```

## C\#

```csharp
// C# Program to DFA that accepts string ending
// with 01 or 10.
using System;

class GFG
{

    // End position is checked using the string
    // length value.
    // `q0` is the starting state.
    // `q1` and `q2` are intermediate states.
    // `q3` and `q4` are final states.
    static void q1(string s, int i)
    {
        Console.Write("q1->");
        if (i == s.Length )
        {
            Console.WriteLine("NO");
            return;
        }

        // state transitions
        // 0 takes to `q1`, 1 takes to `q3`
        if (s[i] == '0')
            q1(s, i + 1);
        else
            q3(s, i + 1);
    }

    static void q2(string s, int i)
    {
        Console.Write("q2->");
        if (i == s.Length)
        {
            Console.WriteLine("NO ");
            return;
        }

        // state transitions
        // 0 takes to `q4`, 1 takes to `q2`
        if (s[i] == '0')
            q4(s, i + 1);
        else
            q2(s, i + 1);
    }

    static void q3(string s, int i)
    {
        Console.Write("q3->");
        if (i == s.Length)
        {
            Console.WriteLine("YES");
            return;
        }

        // state transitions
        // 0 takes to `q4`, 1 takes to `q2`
        if (s[i] == '0')
            q4(s, i + 1);
        else
            q2(s, i + 1);
    }

    static void q4(string s, int i)
    {
        Console.Write("q4->");
        if (i == s.Length)
        {
            Console.WriteLine("YES");
            return;
        }

        // state transitions
        // 0 takes to `q1`, 1 takes to `q3`
        if (s[i] == '0')
            q1(s, i + 1);
        else
            q3(s, i + 1);
    }

    static void q0(string s, int i)
    {
        Console.Write("q0->");
        if (i == s.Length)
        {
            Console.WriteLine("NO");
            return;
        }

        // state transitions
        // 0 takes to `q1`, 1 takes to `q2`
        if (s[i] == '0')
            q1(s, i + 1);
        else
            q2(s, i + 1);
    }

    // Driver Code
    public static void Main()
    {
        string s = "010101";

        // all state transitions are printed.
        // if string is accpetable, YES is printed.
        // else NO is printed
        Console.Write("State transitions are ");
        q0(s, 0);
    }
}

// This code is contributed by AnkitRai01
```

## java 描述语言

```javascript
// JavaScript Program to DFA that accepts string ending
// with 01 or 10.
// End position is checked using the string
// length value.
// `q0` is the starting state.
// `q1` and `q2` are intermediate states.
// `q3` and `q4` are final states.
function q1(s, i) {
    document.write("q1->");
    if (i === s.length) {
        document.write("NO");
        return;
    }

    // state transitions
    // 0 takes to `q1`, 1 takes to `q3`
    if (s[i] === "0") q1(s, i + 1);
    else q3(s, i + 1);
}

function q2(s, i) {
    document.write("q2->");
    if (i === s.length) {
        document.write("NO ");
        return;
    }

    // state transitions
    // 0 takes to `q4`, 1 takes to `q2`
    if (s[i] === "0") q4(s, i + 1);
    else q2(s, i + 1);
}

function q3(s, i) {
    document.write("q3->");
    if (i === s.length) {
        document.write("YES");
        return;
    }

    // state transitions
    // 0 takes to `q4`, 1 takes to `q2`
    if (s[i] === "0") q4(s, i + 1);
    else q2(s, i + 1);
}

function q4(s, i) {
    document.write("q4->");
    if (i === s.length) {
        document.write("YES");
        return;
    }

    // state transitions
    // 0 takes to `q1`, 1 takes to `q3`
    if (s[i] === "0") q1(s, i + 1);
    else q3(s, i + 1);
}

function q0(s, i) {
    document.write("q0->");
    if (i === s.length) {
        document.write("NO");
        return;
    }

    // state transitions
    // 0 takes to `q1`, 1 takes to `q2`
    if (s[i] === "0") q1(s, i + 1);
    else q2(s, i + 1);
}

// Driver Code
var s = "010101";
// all state transitions are printed.
// if string is accpetable, YES is printed.
// else NO is printed
document.write("State transitions are ");
q0(s, 0);
```

**Output:**

```
State transitions are q0->q1->q3->q4->q3->q4->q3->YES
```

**复杂度:** `O(n)`，其中长度为 `n` 的字符串需要遍历 `n` 个状态。
**一个问题陈述可以有多个可能的 DFA。**