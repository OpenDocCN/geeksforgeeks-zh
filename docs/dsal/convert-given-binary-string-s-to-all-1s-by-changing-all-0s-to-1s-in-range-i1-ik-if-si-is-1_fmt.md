# 将二进制字符串 S 转换为全 1 的方法

## 问题描述

给定一个大小为 `N` 的二进制字符串 `S` 和一个数字 `K`，任务是找出是否所有的 `0` 都可以在任意数量的操作中被改变为 `1`。在一次操作中，如果 `S[i]` 最初为 `1`，那么范围 `[i+1, i+K]` 内的所有 `0` 都可以改为 `1`，其中 `0 ≤ i < N-K`。

> 原文: [https://www.geeksforgeeks.org/convert-given-binary-string-s-to-all-1s-by-changing-all-0s-to-1s-in-range-i1-ik-if-si-is-1/](https://www.geeksforgeeks.org/convert-given-binary-string-s-to-all-1s-by-changing-all-0s-to-1s-in-range-i1-ik-if-si-is-1/)

## 示例

**输入:** `S = "100100"`, `N = 6`, `K = 2`
**输出:** YES
**说明:** `S[0]` 可用于将 `S[1]` 和 `S[2]` 变为 1。`S[3]` 可用于将 `S[4]` 和 `S[5]` 变为 1。

**输入:** `S = "110000"`, `N = 6`, `K = 2`
**输出:** NO

## 方法思路

### 天真方法

最简单的方法是以相反的方式遍历字符串，如果遇到 `0`，检查左侧最近的 `1` 的位置是否超过 `K` 个索引。如果是，则打印 `"NO"`。

**时间复杂度:** `O(N*K)`
**辅助空间:** `O(1)`

### 高效方法

为了优化上述方法，思路是使用一个栈。按照以下步骤解决问题:

1.  初始化两个变量 `flag` 和 `count` 分别为 `1` 和 `0`，以存储结果并计数到最后一次出现 `1` 时已更改的 `0` 的数量。
2.  初始化一个空的栈 `st`。
3.  遍历字符串 `S`，并执行以下操作:
    *   如果栈 `st` 为空:
        *   如果当前元素为 `0`，将 `flag` 更改为 `0` 并 `break`，因为此 `0` 不能更改为 `1`。
        *   否则，将 `count` 更新为 `0`，将 `1` 推至 `st`。
    *   否则:
        *   如果当前元素为 `0`，执行以下操作:
            *   将 `count` 增加 1。
            *   如果 `count` 等于 `K`，弹出堆栈 `st` 并将 `count` 更新为 `0`。
        *   否则，将 `count` 更新为 `0`。
4.  如果 `flag` 的值为 `1`，则打印 `"YES"`，否则打印 `"NO"`。

## 代码实现

下面是上述方法的实现:

### C++

```cpp
// C++ program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to check whether all 0s
// in the string can be changed into 1s
void changeCharacters(string S, int N, int K)
{
    int flag = 1;

    // Store the count of 0s converted
    // for the last occurrence of 1
    int count = 0;

    // Declere a stack
    stack<char> st;

    // Traverse the string, S
    for (int i = 0; i < N; i++) {

        // If stack is empty
        if (st.empty()) {

            // There is no 1 that can
            // change this 0 to 1
            if (S[i] == '0') {
                flag = 0;
                break;
            }

            // Push 1 into the stack
            count = 0;
            st.push(S[i]);
        }
        else {
            if (S[i] == '0') {
                count++;

                // The last 1 has reached
                // its limit
                if (count == K) {
                    st.pop();
                    count = 0;
                }
            }

            // New 1 has been found which
            // can now change at most K 0s
            else {
                count = 0;
            }
        }
    }

    // If flag is 1, print "YES"
    // else print "NO"
    if (flag)
        cout << "YES" << endl;
    else
        cout << "NO" << endl;
}

// Driver code
int main()
{
    // Given Input
    string S = "100100";
    int N = S.length();
    int K = 2;

    // Function call
    changeCharacters(S, N, K);

    return 0;
}
```

### Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

// Function to check whether all 0s
// in the string can be changed into 1s
static void changeCharacters(String S, int N, int K)
{
    int flag = 1;

    // Store the count of 0s converted
    // for the last occurrence of 1
    int count = 0;

    // Declere a stack
    Stack<Character> st = new Stack<>(); 

    // Traverse the string, S
    for(int i = 0; i < N; i++)
    {

        // If stack is empty
        if (st.empty())
        {

            // There is no 1 that can
            // change this 0 to 1
            if (S.charAt(i) == '0')
            {
                flag = 0;
                break;
            }

            // Push 1 into the stack
            count = 0;
            st.push(S.charAt(i));
        }
        else
        {
            if (S.charAt(i) == '0')
            {
                count++;

                // The last 1 has reached
                // its limit
                if (count == K)
                {
                    st.pop();
                    count = 0;
                }
            }

            // New 1 has been found which
            // can now change at most K 0s
            else
            {
                count = 0;
            }
        }
    }

    // If flag is 1, print "YES"
    // else print "NO"
    if (flag == 1)
        System.out.print("YES");
    else
        System.out.print("NO");
}

// Driver code
public static void main(String args[])
{

    // Given Input
    String S = "100100";
    int N = S.length();
    int K = 2;

    // Function call
    changeCharacters(S, N, K);
}
}

// This code is contributed by ipg2016107
```

### Python 3

```python
# Python3 program for the above approach

# Function to check whether all 0s
# in the string can be changed into 1s
def changeCharacters(S, N, K):
    flag = 1

    # Store the count of 0s converted
    # for the last occurrence of 1
    count = 0

    # Declere a stack
    st = []

    # Traverse the string, S
    for i in range(N):

        # If stack is empty
        if len(st) == 0:

            # There is no 1 that can
            # change this 0 to 1
            if (S[i] == '0'):
                flag = 0
                break

            # Push 1 into the stack
            count = 0
            st.append(S[i])
        else:
            if (S[i] == '0'):
                count+=1

                # The last 1 has reached
                # its limit
                if (count == K):
                    del st[-1]
                    count = 0

            # New 1 has been found which
            # can now change at most K 0s
            else:
                count = 0

    # If flag is 1, print "YES"
    # else print "NO"
    if (flag):
        print("YES")
    else:
        print("NO")

# Driver code
if __name__ == '__main__':
    # Given Input
    S = "100100"
    N = len(S)
    K = 2

    # Function call
    changeCharacters(S, N, K)

# This code is contributed by mohit kumar 29.
```

### C\#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{

// Function to check whether all 0s
// in the string can be changed into 1s
static void changeCharacters(string S, int N, int K)
{
    int flag = 1;

    // Store the count of 0s converted
    // for the last occurrence of 1
    int count = 0;

    // Declere a stack
    Stack<char> st = new Stack<char>();

    // Traverse the string, S
    for(int i = 0; i < N; i++) {

        // If stack is empty
        if (st.Count==0) {

            // There is no 1 that can
            // change this 0 to 1
            if (S[i] == '0') {
                flag = 0;
                break;
            }

            // Push 1 into the stack
            count = 0;
            st.Push(S[i]);
        }
        else {
            if (S[i] == '0') {
                count++;

                // The last 1 has reached
                // its limit
                if (count == K) {
                    st.Pop();
                    count = 0;
                }
            }

            // New 1 has been found which
            // can now change at most K 0s
            else {
                count = 0;
            }
        }
    }

    // If flag is 1, print "YES"
    // else print "NO"
    if (flag == 1)
       Console.Write("YES");
    else
       Console.Write("NO");
}

// Driver code
public static void Main()
{
    // Given Input
    string S = "100100";
    int N = S.Length;
    int K = 2;

    // Function call
    changeCharacters(S, N, K);

}
}

// This code is contributed by SURENDRA_GANGWAR.
```

## java 描述语言

```javascript
<script>

// JavaScript program for the above approach

// Function to check whether all 0s
// in the string can be changed into 1s
function changeCharacters(S, N, K) {
    let flag = 1;

    // Store the count of 0s converted
    // for the last occurrence of 1
    let count = 0;

    // Declere a stack
    let st = new Array();

    // Traverse the string, S
    for (let i = 0; i < N; i++) {

        // If stack is empty
        if (st.length == 0) {

            // There is no 1 that can
            // change this 0 to 1
            if (S[i] == '0') {
                flag = 0;
                break;
            }

            // Push 1 into the stack
            count = 0;
            st.push(S[i]);
        }
        else {
            if (S[i] == '0') {
                count++;

                // The last 1 has reached
                // its limit
                if (count == K) {
                    st.pop();
                    count = 0;
                }
            }

            // New 1 has been found which
            // can now change at most K 0s
            else {
                count = 0;
            }
        }
    }

    // If flag is 1, print "YES"
    // else print "NO"
    if (flag == 1)
        document.write("YES");
    else
        document.write("NO");
}

// Driver code

// Given Input
let S = "100100";
let N = S.Length;
let K = 2;

// Function call
changeCharacters(S, N, K);

// This code is contributed by _saurabh_jaiswal

</script>
```

`Output`

```
YES
```

`时间复杂度:` O(N)
`辅助空间:` O(1)因为在任何时刻堆栈中最多存在一个字符