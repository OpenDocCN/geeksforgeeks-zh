# 检查一个字符串是否是另一个字符串的子序列（使用 Stacks）

> 原文：[https://www.geeksforgeeks.org/check-if-a-string-is-a-subsequence-of-another-string-using-stacks/](https://www.geeksforgeeks.org/check-if-a-string-is-a-subsequence-of-another-string-using-stacks/)

给定一个字符串 `S`，任务是使用堆栈检查字符串 `target` 是否是字符串 `S` 的子序列。

**示例：**

> **输入：** `S = "KOTTAYAM"`, `target = "KOTA"`
> **输出：** 是
> **说明：** `"KOTA"` 是 `"KOTTAYAM"` 的子序列。
>
> **输入：** `S = "GEEKSFORGEEKS"`, `target = "FORFOR"`
> **输出：** 否

## 方法

按照步骤解决问题：

*   初始化一个栈 `T`。
*   迭代字符串 `target` 的字符，并将它们推入堆栈。

![](img/c21412ec5a39ae189e345cfc6cd68379.png)

*   在反方向上遍历字符串 `S`。
*   如果字符串 `S` 的当前字符与堆栈顶部的字符相同，则弹出堆栈的顶部元素。

![](img/10b4c3bded8ec2ed8d2765c02037364e.png)

![](img/470017b14045364b47060a5d8c67ae8b.png)

![](img/e37834ab25462abeec99847b80cc9fde.png)

![](img/ffdd76a75c30213cc1c2faad148cb3f9.png)

![](img/4e5d22d230c08cd71acba39cc1b9d471.png)

![](img/bdabb1af4d338727e6d984f298b7dd14.png)

![](img/8e47ada0465873fb8b26a4420abaa202.png)

![](img/72c06a794d696339330b2ee1312e9e44.png)

![](img/37a8fc374b7dfc88339d68680de1f554.png)

*   如果在任何时候栈变空，可以断定 `target` 是 `S` 的子序列。
*   否则，`target` 不是 `S` 的子序列。

下面是上述方法的实现：

## C++

```cpp
// C++ Program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check if target
// is a subsequence of string S
void checkforSubsequence(string S,
                         string target)
{

    // Declare a stack
    stack<char> s;

    // Push the characters of
    // target into the stack
    for (int i = 0; i < target.size(); i++) {
        s.push(target[i]);
    }

    // Traverse the string S in reverse
    for (int i = (int)S.size() - 1; i >= 0; i--) {

        // If the stack is empty
        if (s.empty()) {

            cout << "Yes" << endl;
            return;
        }

        // if S[i] is same as the
        // top of the stack
        if (S[i] == s.top()) {

            // Pop the top of stack
            s.pop();
        }
    }

    // Stack s is empty
    if (s.empty())
        cout << "Yes" << endl;
    else
        cout << "No" << endl;
}

// Driver Code
int main()
{
    string S = "KOTTAYAM";
    string target = "KOTA";

    checkforSubsequence(S, target);

    return 0;
}
```

## Java

```java
// Java approach for the above approach
import java.util.Stack;

public class GFG {

    // Function to check if target
    // is a subsequence of string S
    static void checkforSubsequence(String S, String target)
    {

        // Declare a stack
        Stack<Character> s = new Stack<>();

        // Push the characters of
        // target into the stack
        for (int i = 0; i < target.length(); i++) {
            s.push(target.charAt(i));
        }

        // Traverse the string S in reverse
        for (int i = (int)S.length() - 1; i >= 0; i--) {

            // If the stack is empty
            if (s.empty()) {

                System.out.println("Yes");
                return;
            }

            // if S[i] is same as the
            // top of the stack
            if (S.charAt(i) == s.peek()) {

                // Pop the top of stack
                s.pop();
            }
        }

        // Stack s is empty
        if (s.empty())
            System.out.println("Yes");
        else
            System.out.println("No");
    }

    // Driver Code
    public static void main(String[] args)
    {
        String S = "KOTTAYAM";
        String target = "KOTA";

        checkforSubsequence(S, target);
    }
}

// This code is contributed by abhinavjain194
```

## Python 3

```python
# Python3 program for the above approach

# Function to check if target
# is a subsequence of string S
def checkforSubsequence(S, target):

    # Declare a stack
    s = []

    # Push the characters of
    # target into the stack
    for i in range(len(target)):
        s.append(target[i])

    # Traverse the string S in reverse
    for i in range(len(S) - 1, -1, -1):

        # If the stack is empty
        if (len(s) == 0):
            print("Yes")
            return

        # If S[i] is same as the
        # top of the stack
        if (S[i] == s[-1]):

            # Pop the top of stack
            s.pop()

    # Stack s is empty
    if (len(s) == 0):
        print("Yes")
    else:
        print("No")

# Driver Code
if __name__ == "__main__":

    S = "KOTTAYAM"
    target = "KOTA"

    checkforSubsequence(S, target)

# This code is contributed by ukasp
```

## C#

```csharp
// C# approach for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to check if target
// is a subsequence of string S
static void checkforSubsequence(String S,
                                String target)
{

    // Declare a stack
    Stack<char> s = new Stack<char>();

    // Push the characters of
    // target into the stack
    for(int i = 0; i < target.Length; i++)
    {
        s.Push(target[i]);
    }

    // Traverse the string S in reverse
    for(int i = (int)S.Length - 1; i >= 0; i--)
    {

        // If the stack is empty
        if (s.Count == 0)
        {
            Console.WriteLine("Yes");
            return;
        }

        // If S[i] is same as the
        // top of the stack
        if (S[i] == s.Peek())
        {

            // Pop the top of stack
            s.Pop();
        }
    }

    // Stack s is empty
    if (s.Count == 0)
        Console.WriteLine("Yes");
    else
        Console.WriteLine("No");
}

// Driver Code
public static void Main(String[] args)
{
    String S = "KOTTAYAM";
    String target = "KOTA";

    checkforSubsequence(S, target);
}
}

// This code is contributed by shikhasingrajput
```

## JavaScript

```javascript
<script>

// JavaScript Program for the above approach

// Function to check if target
// is a subsequence of string S
function checkforSubsequence(S, target)
{

    // Declare a stack
    var s = [];

    // Push the characters of
    // target into the stack
    for (var i = 0; i < target.length; i++) {
        s.push(target[i]);
    }

    // Traverse the string S in reverse
    for (var i = S.length - 1; i >= 0; i--) {

        // If the stack is empty
        if (s.length==0) {

            document.write( "Yes");
            return;
        }

        // if S[i] is same as the
        // top of the stack
        if (S[i] == s[s.length-1]) {

            // Pop the top of stack
            s.pop();
        }
    }

    // Stack s is empty
    if (s.length==0)
        document.write( "Yes" );
    else
        document.write( "No" );
}

// Driver Code

var S = "KOTTAYAM";
var target = "KOTA";
checkforSubsequence(S, target);

</script>
```

**输出：**

```
Yes
```

**时间复杂度：** `O(N)`
**辅助空间：** `O(N)`