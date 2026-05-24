# 通过重复删除给定的子序列

## 检查字符串是否可以为空

> 原文: [https://www.geeksforgeeks.org/check-if-a-string-can-be-made-empty-by-repeatedly-removing-given-subsequence/](https://www.geeksforgeeks.org/check-if-a-string-can-be-made-empty-by-repeatedly-removing-given-subsequence/)

给定一个仅包含字符`G`和`F`的字符串`str`，任务是在移除形式为`GFG`的所有子序列后，检查给定的字符串`str`是否可以为空。

**示例:**

> **输入:** `N = 6`, `str[] = "GFGFGG"`
> **输出:** 是
> **说明:** 两串“GFG”可以移除，第一串有索引{0, 1, 5}，第二串有剩余索引。
>
> **输入:** `N = 10`, `str = "ggffgffg"`
> **输出:** 否
> **说明:** 是不可能的，因为即使移除了所有可能的子串，还会剩下一个`F`。

**方法:** 可以看出，为了制作`GFG`，需要2个`G`和中间的一个`F`，所以如果`G`的计数不等于`F`的计数的两倍，就永远不可能从给定的字符串中制作出一些数量的`GFG`来完成。还有一点需要检查的是，从左到右遍历时，`G`的个数一定不能小于`F`的个数。例如字符串是`gggffgffg`，可以看到最后两个字符是`FF`，但前面只有一个`G`，所以不可能从这两个`F`中造出`GFG`，所以答案还是否定的。

最后一个需要检查的条件是，为了按照以下步骤解决问题：

*   将变量`countG`和`countF`初始化为`0`，将`G`和`F`的计数存储在字符串`str[]`中。
*   使用变量`i`迭代范围`[0, N]`，并执行以下步骤：
    *   如果`str[i]`等于`G`，那么将`countG`的值增加`1`，否则将`countF`的值增加`1`。
*   如果`2 * countF`不等于`countG`，那么就不可能，打印“否”并返回。
*   将变量`id`初始化为`0`，用于计算`G`和`F`的计数直到某个特定的索引，并将变量`flag`设置为`true`来存储答案。
*   使用变量`i`迭代范围`[0, N]`，并执行以下步骤：
    *   如果`str[i]`等于`'G'`，则将`countG`的值减少`1`，将`id`的值增加`1`。
    *   否则，将`countF`的值减少`1`，将`id`的值减少`1`。
    *   如果`id`小于`0`，则多余的`G`最终将不会被利用，因此将`flag`的值设置为`false`并`break`。
    *   如果`countG`小于`countF`，那么多余的`F`最终将不会被利用，所以将`flag`的值设置为`false`并`break`。
*   如果`flag`等于`true`，则打印“是”，否则打印“否”。

下面是上述方法的实现。

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to check if a string can be
// made empty by removing all
// subsequences of the form "GFG" or not
void findIfPossible(int N, string str)
{
    int countG = 0, countF = 0;
    for (int i = 0; i < N; i++) {

        if (str[i] == 'G')
            countG++;
        else
            countF++;
    }

    if (2 * countF != countG) {
        cout << "NO\n";
    }
    else {

        int id = 0;
        bool flag = true;

        for (int i = 0; i < N; i++) {

            if (str[i] == 'G') {

                countG--;
                id++;
            }
            else {

                countF--;
                id--;
            }
            if (id < 0) {

                flag = false;
                break;
            }
            if (countG < countF) {

                flag = false;
                break;
            }
        }

        if (flag) {

            cout << "YES\n";
        }
        else {
            cout << "NO\n";
        }
    }
}

// Driver Code
int main()
{
    int n = 6;
    string str = "GFGFGG";

    findIfPossible(n, str);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.io.*;

class GFG
{

    // Function to check if a string can be
    // made empty by removing all
    // subsequences of the form "GFG" or not
    public static void findIfPossible(int N, String str)
    {
        int countG = 0, countF = 0;
        for (int i = 0; i < N; i++) {

            if (str.charAt(i) == 'G')
                countG++;
            else
                countF++;
        }

        if (2 * countF != countG) {
            System.out.println("No");
        }
        else {

            int id = 0;
            boolean flag = true;

            for (int i = 0; i < N; i++) {

                if (str.charAt(i) == 'G') {

                    countG--;
                    id++;
                }
                else {

                    countF--;
                    id--;
                }
                if (id < 0) {

                    flag = false;
                    break;
                }
                if (countG < countF) {

                    flag = false;
                    break;
                }
            }

            if (flag) {

                System.out.println("Yes");
            }
            else {
                System.out.println("No");
            }
        }
    }

    public static void main(String[] args)
    {
        int n = 6;
        String str = "GFGFGG";
        findIfPossible(n, str);
    }
}

// This code is contributed by maddler.
```

## Python 3

```python
# Python3 program for the above approach

# Function to check if a string can be
# made empty by removing all subsequences
# of the form "GFG" or not
def findIfPossible(N, str_):

    countG = 0
    countF = 0

    for i in range(N):
        if str_[i] == 'G':
            countG += 1
        else:
            countF += 1

    if 2 * countF != countG:
        print("NO")
    else:
        id = 0
        flag = True

        for i in range(N):
            if str_[i] == 'G':
                countG -= 1
                id += 1
            else:
                countF -= 1
                id -= 1
            if id < 0:
                flag = False
                break
            if countG < countF:
                flag = False
                break

        if flag:
            print("YES")
        else:
            print("NO")

# Driver Code
n = 6
str_ = "GFGFGG"

findIfPossible(n, str_)

# This code is contributed by Parth Manchanda
```

## C#

```csharp
// C# program for the above approach
using System;
using System.Collections.Generic;

class GFG{
// Function to check if a string can be
// made empty by removing all
// subsequences of the form "GFG" or not
static void findIfPossible(int N, string str)
{
    int countG = 0, countF = 0;
    for (int i = 0; i < N; i++) {

        if (str[i] == 'G')
            countG++;
        else
            countF++;
    }

    if (2 * countF != countG) {
        Console.WriteLine("NO");
    }
    else {

        int id = 0;
        bool flag = true;

        for (int i = 0; i < N; i++) {

            if (str[i] == 'G') {

                countG--;
                id++;
            }
            else {

                countF--;
                id--;
            }
            if (id < 0) {

                flag = false;
                break;
            }
            if (countG < countF) {

                flag = false;
                break;
            }
        }

        if (flag) {

            Console.WriteLine("YES");
        }
        else {
            Console.WriteLine("NO");
        }
    }
}

// Driver Code
public static void Main()
{
    int n = 6;
    string str = "GFGFGG";
    findIfPossible(n, str);
}
}

// This code is contributed by ipg2016107.
```

## java 描述语言

```javascript
<script>

// JavaScript program for the above approach;

// Function to check if a string can be
// made empty by removing all
// subsequences of the form "GFG" or not
function findIfPossible(N, str)
{
    let countG = 0, countF = 0;
    for(let i = 0; i < N; i++)
    {
        if (str[i] == 'G')
            countG++;
        else
            countF++;
    }

    if (2 * countF != countG)
    {
        document.write("NO");
    }
    else
    {
        let id = 0;
        let flag = true;

        for(let i = 0; i < N; i++)
        {
            if (str[i] == 'G')
            {
                countG--;
                id++;
            }
            else
            {
                countF--;
                id--;
            }
            if (id < 0)
            {
                flag = false;
                break;
            }
            if (countG < countF)
            {
                flag = false;
                break;
            }
        }

        if (flag)
        {
            document.write("YES");
        }
        else
        {
            document.write("NO");
        }
    }
}

// Driver Code
let n = 6;
let str = "GFGFGG";

findIfPossible(n, str);

// This code is contributed by Potta Lokesh

</script>
```

**Output:**
```
YES
```

时间复杂度: `O(N)`
空间复杂度: `O(1)`