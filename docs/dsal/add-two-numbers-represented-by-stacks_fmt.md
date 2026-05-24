# 加两个栈代表的数字

> 原文: [https://www.geeksforgeeks.org/add-two-numbers-represented-by-stacks/](https://www.geeksforgeeks.org/add-two-numbers-represented-by-stacks/)

给定由两个栈表示的两个数字 `N1` 和 `N2`，使得它们的最高有效位出现在栈底，任务是以栈的形式计算并返回两个数的和。

## 示例

**输入:** `N1 = {5, 8, 7, 4}`，`N2 = {2, 1, 3}`
**输出:** `{6, 0, 8, 7}`
**解释:**
步骤 1: 从 `N1` 弹出元素 (= 4) + 从 `N2` 弹出元素 (= 3) = `{7}`
步骤 2: 从 `N1` 弹出元素 (= 7) + 从 `N2` 弹出元素 (= 1) = `{7, 8}`，`rem=0`。
步骤 3: 从 `N1` 弹出元素 (= 8) + 从 `N2` 弹出元素 (= 2) = `{7, 8, 0}` 和 `rem=1`。
步骤 4: 从 `N1` 弹出元素 (= 5) = `{7, 8, 0, 6}`。
在堆叠反转时，获得所需的排列 `{6, 0, 8, 7}`。

**输入:** `N1 = {6, 4, 9, 5, 7}`，`N2 = {2, 1, 3}`
**输出:** `{6, 5, 0, 0, 5}`

## 方法

利用[将链表表示的两个数字相加](https://www.geeksforgeeks.org/sum-of-two-linked-lists/?ref=rp)的概念，即可解决问题。按照以下步骤解决问题。

1.  创建一个新的堆栈 `res` 来存储两个堆栈的总和。
2.  初始化变量 `rem` 和 `sum` 分别存储生成的进位和顶部元素的和。
3.  继续弹出两个堆栈的顶部元素，并将 `sum % 10` 推至 `res`，并将 `rem` 更新为 `sum / 10`。
4.  重复上述步骤，直到堆栈为空。如果 `rem` 大于 `0`，则将 `rem` 插入堆栈。
5.  反转 `res` 堆栈，使最高有效位出现在 `res` 堆栈的底部。

下面是最终方法的实现：

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to return the stack that
// contains the sum of two numbers
stack<int> addStack(stack<int> N1,
                    stack<int> N2)
{
    stack<int> res;
    int sum = 0, rem = 0;

    while (!N1.empty() and !N2.empty()) {

      // Calculate the sum of the top
      // elements of both the stacks
        sum = (rem + N1.top() + N2.top());

      // Push the sum into the stack
        res.push(sum % 10);

      // Store the carry
        rem = sum / 10;

      // Pop the top elements
        N1.pop();
        N2.pop();
    }

    // If N1 is not empty
    while (!N1.empty()) {
        sum = (rem + N1.top());
        res.push(sum % 10);
        rem = sum / 10;
        N1.pop();
    }
    // If N2 is not empty
    while (!N2.empty()) {
        sum = (rem + N2.top());
        res.push(sum % 10);
        rem = sum / 10;
        N2.pop();
    }

    // If carry remains
    while (rem > 0) {
        res.push(rem);
        rem /= 10;
    }

    // Reverse the stack.so that
    // most significant digit is
    // at the bottom of the stack
    while (!res.empty()) {
        N1.push(res.top());
        res.pop();
    }
    res = N1;
    return res;
}

// Function to display the
// resultant stack
void display(stack<int>& res)
{
    int N = res.size();
    string s = "";
    while (!res.empty()) {
        s = to_string(res.top()) + s;
        res.pop();
    }

  cout << s << endl;
}

// Driver Code
int main()
{
    stack<int> N1;
    N1.push(5);
    N1.push(8);
    N1.push(7);
    N1.push(4);

    stack<int> N2;
    N2.push(2);
    N2.push(1);
    N2.push(3);

    stack<int> res = addStack(N1, N2);

    display(res);

    return 0;
}
```

## Java

```java
// Java program to implement
// the above approach
import java.util.Stack;
class GFG{

    // Function to return the stack that
    // contains the sum of two numbers
    static Stack<Integer> addStack(Stack<Integer> N1,
                                   Stack<Integer> N2)
    {
        Stack<Integer> res = new Stack<Integer>();
        int sum = 0, rem = 0;
        while (!N1.isEmpty() && !N2.isEmpty())
        {

            // Calculate the sum of the top
            // elements of both the stacks
            sum = (rem + N1.peek() + N2.peek());

            // Push the sum into the stack
            res.add(sum % 10);

            // Store the carry
            rem = sum / 10;

            // Pop the top elements
            N1.pop();
            N2.pop();
        }

        // If N1 is not empty
        while (!N1.isEmpty())
        {
            sum = (rem + N1.peek());
            res.add(sum % 10);
            rem = sum / 10;
            N1.pop();
        }

          // If N2 is not empty
        while (!N2.isEmpty())
        {
            sum = (rem + N2.peek());
            res.add(sum % 10);
            rem = sum / 10;
            N2.pop();
        }

        // If carry remains
        while (rem > 0)
        {
            res.add(rem);
            rem /= 10;
        }

        // Reverse the stack.so that
        // most significant digit is
        // at the bottom of the stack
        while (!res.isEmpty())
        {
            N1.add(res.peek());
            res.pop();
        }
        res = N1;
        return res;
    }

    // Function to display the
    // resultant stack
    static void display(Stack<Integer> res)
    {
        int N = res.size();
        String s = "";
        while (!res.isEmpty())
        {
            s = String.valueOf(res.peek()) + s;
            res.pop();
        }

        System.out.print(s + "\n");
    }

    // Driver Code
    public static void main(String[] args)
    {
        Stack<Integer> N1 = new Stack<Integer>();
        N1.add(5);
        N1.add(8);
        N1.add(7);
        N1.add(4);
          Stack<Integer> N2 = new Stack<Integer>();
        N2.add(2);
        N2.add(1);
        N2.add(3);
          Stack<Integer> res = addStack(N1, N2);
          display(res);
    }
}

// This code is contributed by shikhasingrajput
```

## Python 3

```python
# Python3 program to implement
# the above approach

# Function to return the stack that
# contains the sum of two numbers
def addStack(N1, N2):

    res = []
    s = 0
    rem = 0

    while (len(N1) != 0 and len(N2) != 0):

        # Calculate the sum of the top
        # elements of both the stacks
        s = (rem + N1[-1] + N2[-1])

        # Push the sum into the stack
        res.append(s % 10)

        # Store the carry
        rem = s // 10

        # Pop the top elements
        N1.pop(-1)
        N2.pop(-1)

    # If N1 is not empty
    while(len(N1) != 0):
        s = rem + N1[-1]
        res.append(s % 10)
        rem = s // 10
        N1.pop(-1)

    # If N2 is not empty
    while(len(N2) != 0):
        s = rem + N2[-1]
        res.append(s % 10)
        rem = s // 10
        N2.pop(-1)

    # If carry remains
    while(rem > 0):
        res.append(rem)
        rem //= 10

    # Reverse the stack.so that
    # most significant digit is
    # at the bottom of the stack
    res = res[::-1]

    return res

# Function to display the
# resultant stack
def display(res):

    s = ""
    for i in res:
        s += str(i)

    print(s)

# Driver Code
N1 = []
N1.append(5)
N1.append(8)
N1.append(7)
N1.append(4)

N2 = []
N2.append(2)
N2.append(1)
N2.append(3)

# Function call
res = addStack(N1, N2)

display(res)

# This code is contributed by Shivam Singh
```

## C#

```csharp
// C# program to implement
// the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to return the stack that
// contains the sum of two numbers
static Stack<int> PushStack(Stack<int> N1,
                            Stack<int> N2)
{
    Stack<int> res = new Stack<int>();
    int sum = 0, rem = 0;

    while (N1.Count != 0 && N2.Count != 0)
    {

        // Calculate the sum of the top
        // elements of both the stacks
        sum = (rem + N1.Peek() + N2.Peek());

        // Push the sum into the stack
        res.Push((int)sum % 10);

        // Store the carry
        rem = sum / 10;

        // Pop the top elements
        N1.Pop();
        N2.Pop();
    }

    // If N1 is not empty
    while (N1.Count != 0)
    {
        sum = (rem + N1.Peek());
        res.Push(sum % 10);
        rem = sum / 10;
        N1.Pop();
    }

    // If N2 is not empty
    while (N2.Count != 0)
    {
        sum = (rem + N2.Peek());
        res.Push(sum % 10);
        rem = sum / 10;
        N2.Pop();
    }

    // If carry remains
    while (rem > 0)
    {
        res.Push(rem);
        rem /= 10;
    }

    // Reverse the stack.so that
    // most significant digit is
    // at the bottom of the stack
    while (res.Count != 0)
    {
        N1.Push(res.Peek());
        res.Pop();
    }

    res = N1;
    return res;
}

// Function to display the
// resultamt stack
static void display(Stack<int> res)
{
    int N = res.Count;
    String s = "";

    while (res.Count != 0)
    {
        s = String.Join("", res.Peek()) + s;
        res.Pop();
    }

    Console.Write(s + "\n");
}

// Driver Code
public static void Main(String[] args)
{
    Stack<int> N1 = new Stack<int>();
    N1.Push(5);
    N1.Push(8);
    N1.Push(7);
    N1.Push(4);

    Stack<int> N2 = new Stack<int>();
    N2.Push(2);
    N2.Push(1);
    N2.Push(3);

    Stack<int> res = PushStack(N1, N2);

    display(res);
}
}

// This code is contributed by Amit Katiyar
```

## JavaScript

```javascript
// JavaScript program to implement
// the above approach

// Function to return the stack that
// contains the sum of two numbers
function addStack(N1, N2)
{
    var res = [];
    var sum = 0, rem = 0;

    while (N1.length!=0 && N2.length!=0) { 

      // Calculate the sum of the top
      // elements of both the stacks
        sum = (rem + N1[N1.length-1] +N2[N2.length-1]);

      // Push the sum into the stack
        res.push(sum % 10);

      // Store the carry
        rem = parseInt(sum / 10);

      // Pop the top elements
        N1.pop();
        N2.pop();
    }

    // If N1 is not empty
    while (N1.length!=0) {
        sum = (rem + N1[N1.length-1]);
        res.push(sum % 10);
        rem = parseInt(sum / 10);
        N1.pop();
    }
    // If N2 is not empty
    while (N2.length!=0) {
        sum = (rem +N2[N2.length-1]);
        res.push(sum % 10);
        rem = parseInt(sum / 10);
        N2.pop();
    }

    // If carry remains
    while (rem > 0) {
        res.push(rem);
        rem = parseInt(rem/10);
    }

    // Reverse the stack.so that
    // most significant digit is
    // at the bottom of the stack
    while (res.length!=0) {
        N1.push(res[res.length-1]);
        res.pop();
    }
    res = N1;
    return res;
}

// Function to display the
// resultamt stack
function display(res)
{
    var N = res.length;
    var s = "";
    while (res.length!=0) {
        s = (res[res.length-1].toString()) + s;
        res.pop();
    }

  document.write( s );
}

// Driver Code
var N1 = [];
N1.push(5);
N1.push(8);
N1.push(7);
N1.push(4);
var N2 = [];
N2.push(2);
N2.push(1);
N2.push(3);
var res = addStack(N1, N2);
display(res);
```

**Output:**

```
4785 + 312 = 5097
```

时间复杂度：`O(N)`
辅助空间：`O(N)`