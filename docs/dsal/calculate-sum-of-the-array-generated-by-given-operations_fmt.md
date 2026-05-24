# 计算给定运算生成的数组之和

> 原文: [https://www.geeksforgeeks.org/calculate-sum-of-the-array-generated-by-given-operations/](https://www.geeksforgeeks.org/calculate-sum-of-the-array-generated-by-given-operations/)

给定一个由 `N` [字符串](https://www.geeksforgeeks.org/string-data-structure/)组成的[数组](https://www.geeksforgeeks.org/introduction-to-arrays/) `arr[]`，任务是在[遍历给定数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/) `arr[]`的同时，通过执行以下操作找到数组`brr[]`（*初始为空*）的总和：

*   如果[数组](https://www.geeksforgeeks.org/array-data-structure/) `arr[]`包含一个整数，则将该整数插入到数组 `brr[]`中。
*   如果数组 `arr[]`有字符串`"+"`，则将数组 `brr[]`中最后两个元素的和插入到数组 `brr[]`中。
*   如果数组 `arr[]`有字符串`"D"`，则将数组 `brr[]`最后一个元素的两倍值插入到数组 `brr[]`中。
*   如果数组 `arr[]`有字符串`"C"`，则将数组 `brr[]`的最后一个元素移除。

## 示例

> **输入:** `arr[] = {"5", "2", "C", "D", "+"}`
> **输出:** 30
> **解释:**
> 遍历数组 `arr[]`时，数组 `brr[]`修改为：
> *   `"5"` - 向数组`brr[]`中添加5。现在，数组`brr[]`修改为`{5}`。
> *   `"2"` - 向数组`brr[]`中添加2。现在，数组`brr[]`修改为`{5, 2}`。
> *   `"C"` - 从数组中移除最后一个元素。现在，数组`brr[]`修改为`{5}`。
> *   `"D"` - 将数组`brr[]`的最后一个元素的两倍添加到数组`brr[]`中。现在，数组`brr[]`修改为`{5, 10}`。
> *   `"+"` – 将数组`brr[]`的最后两个元素之和加到数组`brr[]`上。现在，数组`brr[]`修改为`{5, 10, 15}`。
>
> 执行上述操作后，数组`brr[]`的总和为 `5 + 10 + 15 = 30`。

> **输入:** `arr[] = {"5", "-2", "4", "C", "D", "9", "+", "+"}`
> **输出:** 27

## 方法

解决给定问题的思路是使用[栈](https://www.geeksforgeeks.org/stack-data-structure/)。按照以下步骤解决问题：

*   初始化一个整数栈，比如说 `S`，初始化一个变量，比如说 `ans` 为 `0`，存储形成的数组的和。
*   [遍历给定数组](https://www.geeksforgeeks.org/c-program-to-traverse-an-array/) `arr[]`，并执行以下步骤：
    *   如果`arr[i]`的值为`"C"`，则从 `ans` 中减去栈的顶部元素，并从 `S` 中弹出。
    *   如果`arr[i]`的值为`"D"`，则将栈 `S` 的顶部元素的值乘以二，然后将其值添加到 `ans` 中。
    *   如果`arr[i]`的值为`"+"`，则计算栈 `S` 的前两个元素的和，并将其和加到 `ans` 上。
    *   否则，将`arr[i]`推送到栈 `S`，并将其值添加到 `ans` 中。
*   循环结束后，打印`ans`的值作为结果。

下面是上述方法的实现：

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find the sum of the array
// formed by performing given set of
// operations while traversing the array ops[]
void findTotalSum(vector<string>& ops)
{
    // If the size of array is 0
    if (ops.empty()) {
        cout << 0;
        return;
    }

    stack<int> pts;

    // Stores the required sum
    int ans = 0;

    // Traverse the array ops[]
    for (int i = 0; i < ops.size(); i++) {

        // If the character is C, remove
        // the top element from the stack
        if (ops[i] == "C") {

            ans -= pts.top();
            pts.pop();
        }

        // If the character is D, then push
        // 2 * top element into stack
        else if (ops[i] == "D") {

            pts.push(pts.top() * 2);
            ans += pts.top();
        }

        // If the character is +, add sum
        // of top two elements from the stack
        else if (ops[i] == "+") {

            int a = pts.top();
            pts.pop();
            int b = pts.top();
            pts.push(a);
            ans += (a + b);
            pts.push(a + b);
        }

        // Otherwise, push x
        // and add it to ans
        else {
            int n = stoi(ops[i]);
            ans += n;
            pts.push(n);
        }
    }

    // Print the resultant sum
    cout << ans;
}

// Driver Code
int main()
{
    vector<string> arr = { "5", "-2", "C", "D", "+" };
    findTotalSum(arr);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.io.*;
import java.lang.*;
import java.util.*;

class GFG
{

  // Function to find the sum of the array
  // formed by performing given set of
  // operations while traversing the array ops[]
  static void findTotalSum(String ops[])
  {

    // If the size of array is 0
    if (ops.length == 0)
    {
      System.out.println(0);
      return;
    }

    Stack<Integer> pts = new Stack<>();

    // Stores the required sum
    int ans = 0;

    // Traverse the array ops[]
    for (int i = 0; i < ops.length; i++) {

      // If the character is C, remove
      // the top element from the stack
      if (ops[i] == "C") {

        ans -= pts.pop();
      }

      // If the character is D, then push
      // 2 * top element into stack
      else if (ops[i] == "D") {

        pts.push(pts.peek() * 2);
        ans += pts.peek();
      }

      // If the character is +, add sum
      // of top two elements from the stack
      else if (ops[i] == "+") {

        int a = pts.pop();
        int b = pts.peek();
        pts.push(a);
        ans += (a + b);
        pts.push(a + b);
      }

      // Otherwise, push x
      // and add it to ans
      else {
        int n = Integer.parseInt(ops[i]);
        ans += n;
        pts.push(n);
      }
    }

    // Print the resultant sum
    System.out.println(ans);
  }

  // Driver Code
  public static void main(String[] args)
  {

    String arr[] = { "5", "-2", "C", "D", "+" };
    findTotalSum(arr);
  }
}

// This code is contributed by Kingash.
```

### Python 3

```python
# Python3 program for the above approach

# Function to find the sum of the array
# formed by performing given set of
# operations while traversing the array ops[]
def findTotalSum(ops):

    # If the size of array is 0
    if (len(ops) == 0):
        print(0)
        return

    pts = []

    # Stores the required sum
    ans = 0

    # Traverse the array ops[]
    for i in range(len(ops)):

        # If the character is C, remove
        # the top element from the stack
        if (ops[i] == "C"):

            ans -= pts[-1]
            pts.pop()

        # If the character is D, then push
        # 2 * top element into stack
        elif (ops[i] == "D"):

            pts.append(pts[-1] * 2)
            ans += pts[-1]

        # If the character is +, add sum
        # of top two elements from the stack
        elif (ops[i] == "+"):

            a = pts[-1]
            pts.pop()
            b = pts[-1]
            pts.append(a)
            ans += (a + b)
            pts.append(a + b)

        # Otherwise, push x
        # and add it to ans
        else:
            n = int(ops[i])
            ans += n
            pts.append(n)

    # Print the resultant sum
    print(ans)

# Driver Code
if __name__ == "__main__":

    arr = ["5", "-2", "C", "D", "+"]
    findTotalSum(arr)

    # This code is contributed by ukasp.
```

## C#

```
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to find the sum of the array
// formed by performing given set of
// operations while traversing the array ops[]
static void findTotalSum(string []ops)
{

    // If the size of array is 0
    if (ops.Length == 0)
    {
        Console.WriteLine(0);
        return;
    }

    Stack<int> pts = new Stack<int>();

    // Stores the required sum
    int ans = 0;

    // Traverse the array ops[]
    for(int i = 0; i < ops.Length; i++)
    {

        // If the character is C, remove
        // the top element from the stack
        if (ops[i] == "C")
        {
            ans -= pts.Pop();
        }

        // If the character is D, then push
        // 2 * top element into stack
        else if (ops[i] == "D")
        {
            pts.Push(pts.Peek() * 2);
            ans += pts.Peek();
        }

        // If the character is +, add sum
        // of top two elements from the stack
        else if (ops[i] == "+")
        {
            int a = pts.Pop();
            int b = pts.Peek();
            pts.Push(a);
            ans += (a + b);
            pts.Push(a + b);
        }

        // Otherwise, push x
        // and add it to ans
        else
        {
            int n = Int32.Parse(ops[i]);
            ans += n;
            pts.Push(n);
        }
    }

    // Print the resultant sum
    Console.WriteLine(ans);
}

// Driver Code
public static void Main()
{
    string []arr = { "5", "-2", "C", "D", "+" };

    findTotalSum(arr);
}
}

// This code is contributed by ipg2016107
```

## JavaScript

```
<script>

// JavaScript program for the above approach

// Function to find the sum of the array
// formed by performing given set of
// operations while traversing the array ops[]
function findTotalSum(ops)
{
    // If the size of array is 0
    if (ops.length==0) {
        document.write( 0);
        return;
    }

    var pts = [];

    // Stores the required sum
    var ans = 0;

    // Traverse the array ops[]
    for (var i = 0; i < ops.length; i++) {

        // If the character is C, remove
        // the top element from the stack
        if (ops[i] == "C") {

            ans -= pts[pts.length-1];
            pts.pop();
        }

        // If the character is D, then push
        // 2 * top element into stack
        else if (ops[i] == "D") {

            pts.push(pts[pts.length-1] * 2);
            ans += pts[pts.length-1];
        }

        // If the character is +, add sum
        // of top two elements from the stack
        else if (ops[i] == "+") {

            var a = pts[pts.length-1];
            pts.pop();
            var b = pts[pts.length-1];
            pts.push(a);
            ans += (a + b);
            pts.push(a + b);
        }

        // Otherwise, push x
        // and add it to ans
        else {
            var n = parseInt(ops[i]);
            ans += n;
            pts.push(n);
        }
    }

    // Print the resultant sum
    document.write( ans);
}

// Driver Code

var arr = ["5", "-2", "C", "D", "+" ];
findTotalSum(arr);

</script>
```

`Output:`

`时间复杂度:` `O(N)`
`辅助空间:` `O(N)`