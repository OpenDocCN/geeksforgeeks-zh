# 在 O(1) 空间找到字符串中的重复字符

> 原文：[https://www.geeksforgeeks.org/find-the-duplicate-characters-in-a-string-in-o1-space/](https://www.geeksforgeeks.org/find-the-duplicate-characters-in-a-string-in-o1-space/)

给定一个[字符串](https://www.geeksforgeeks.org/string-data-structure/) `str`，任务是在不使用任何额外数据结构的情况下，按照字典顺序查找给定字符串中存在的所有重复字符。

**示例：**

> **输入：** `str = "geeksforgeeks"`
> **输出：** e g k s
> **解释：**
> 字符 `'g'` 的频率 = 2
> 字符 `'e'` 的频率 = 4
> 字符 `'k'` 的频率 = 2
> 字符 `'s'` 的频率 = 2
> 因此，需要的输出为 **e k s**。
>
> **输入：** `str = "apple"`
> **输出：** p
> **解释：**
> 字符 `'p'` 的频率 = 2。
> 所以需要的输出是 **p**。

**方法：** 按照以下步骤解决问题：

*   初始化一个变量，比如 `first`，其中 `first` 的第 `i` 位检查字符串中的字符 `(i + 'a')` 是否至少出现一次。
*   初始化一个变量，比如 `second`，其中 `second` 的第 `i` 位检查字符串中的字符 `(i + 'a')` 是否至少出现两次。
*   [迭代字符串的字符](https://www.geeksforgeeks.org/iterate-over-characters-of-a-string-in-c/)。对于每一个第 `i` 个字符，检查字符串中是否已经出现 `str[i]`。如果发现为真，则[设置 `second`](https://www.geeksforgeeks.org/set-k-th-bit-given-number/) 的 `(str[i] - 'a')` 第 `i` 位。
*   否则，[设置 `first`](https://www.geeksforgeeks.org/set-k-th-bit-given-number/) 的 `(str[i] - 'a')` 第 `i` 位。
*   最后，遍历 `[0, 25]` 范围，检查 `first` 和 `second` 的第 `i` 位是否都已[设置](https://www.geeksforgeeks.org/check-whether-k-th-bit-set-not/)。如果发现为真，则打印 `(i + 'a')`。

下面是上述方法的实现：

## C++

```cpp
// C++ program to implement
// the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to find duplicate characters
// in string without using any additional
// data structure
void findDuplicate(string str, int N)
{

    // Check if (i + 'a') is present
    // in str at least once or not.
    int first = 0;

    // Check if (i + 'a') is present
    // in str at least twice or not.
    int second = 0;

    // Iterate over the characters
    // of the string str
    for (int i = 0; i < N; i++) {

        // If str[i] has already occurred in str
        if (first & (1 << (str[i] - 'a'))) {

            // Set (str[i] - 'a')-th bit of second
            second
                = second | (1 << (str[i] - 'a'));
        }
        else {

            // Set (str[i] - 'a')-th bit of second
            first
                = first | (1 << (str[i] - 'a'));
        }
    }

    // Iterate over the range [0, 25]
    for (int i = 0; i < 26; i++) {

        // If i-th bit of both first
        // and second is Set
        if ((first & (1 << i))
            && (second & (1 << i))) {

            cout << char(i + 'a') << " ";
        }
    }
}

// Driver Code
int main()
{
    string str = "geeksforgeeks";
    int N = str.length();

    findDuplicate(str, N);
}
```

## Java

```java
// Java program for the above approach
public class GFG
{

  // Function to find duplicate characters
  // in string without using any additional
  // data structure
  static void findDuplicate(String str, int N)
  {

    // Check if (i + 'a') is present
    // in str at least once or not.
    int first = 0;

    // Check if (i + 'a') is present
    // in str at least twice or not.
    int second = 0;

    // Iterate over the characters
    // of the string str
    for (int i = 0; i < N; i++)
    {

      // If str[i] has already occurred in str
      if ((first & (1 << (str.charAt(i) - 'a'))) != 0)
      {

        // Set (str[i] - 'a')-th bit of second
        second
          = second | (1 << (str.charAt(i) - 'a'));
      }
      else
      {

        // Set (str[i] - 'a')-th bit of second
        first
          = first | (1 << (str.charAt(i) - 'a'));
      }
    }

    // Iterate over the range [0, 25]
    for (int i = 0; i < 26; i++)
    {

      // If i-th bit of both first
      // and second is Set
      if (((first & (1 << i))
           & (second & (1 << i))) != 0) {

        System.out.print((char)(i + 'a') + " ");
      }
    }
  }

  // Driver Code
  static public void main(String args[])
  {
    String str = "geeksforgeeks";
    int N = str.length();

    findDuplicate(str, N);
  }
}

// This code is contributed by AnkThon.
```

## Python 3

```python
# Python 3 code added. program to implement
# the above approach

# Function to find duplicate characters
# in str1ing without using any additional
# data str1ucture
def findDuplicate(str1, N):

    # Check if (i + 'a') is present
    # in str1 at least once or not.
    first = 0

    # Check if (i + 'a') is present
    # in str1 at least twice or not.
    second = 0

    # Iterate over the characters
    # of the str1ing str1
    for i in range(N):

        # If str1[i] has already occurred in str1
        if (first & (1 << (ord(str1[i]) - 97))):

            # Set (str1[i] - 'a')-th bit of second
            second = second | (1 << (ord(str1[i]) - 97))
        else:
            # Set (str1[i] - 'a')-th bit of second
            first = first | (1 << (ord(str1[i]) - 97))

    # Iterate over the range [0, 25]
    for i in range(26):

        # If i-th bit of both first
        # and second is Set
        if ((first & (1 << i)) and (second & (1 << i))):
            print(chr(i + 97), end = " ")

# Driver Code
if __name__ == '__main__':
    str1 = "geeksforgeeks"
    N = len(str1)
    findDuplicate(str1, N)

    # This code is contributed by SURENDRA_GANGWAR.
```

## C#

```csharp
// C# program for the above approach
using System;
class GFG
{

  // Function to find duplicate characters
  // in string without using any additional
  // data structure
  static void findDuplicate(string str, int N)
  {

    // Check if (i + 'a') is present
    // in str at least once or not.
    int first = 0;

    // Check if (i + 'a') is present
    // in str at least twice or not.
    int second = 0;

    // Iterate over the characters
    // of the string str
    for (int i = 0; i < N; i++) {

      // If str[i] has already occurred in str
      if ((first & (1 << (str[i] - 'a'))) != 0)
      {

        // Set (str[i] - 'a')-th bit of second
        second
          = second | (1 << (str[i] - 'a'));
      }
      else
      {

        // Set (str[i] - 'a')-th bit of second
        first
          = first | (1 << (str[i] - 'a'));
      }
    }

    // Iterate over the range [0, 25]
    for (int i = 0; i < 26; i++)
    {

      // If i-th bit of both first
      // and second is Set
      if (((first & (1 << i))
           & (second & (1 << i))) != 0) {

        Console.Write((char)(i + 'a') + " ");
      }
    }
  }

  // Driver Code
  static public void Main()
  {
    string str = "geeksforgeeks";
    int N = str.Length;

    findDuplicate(str, N);
  }
}

// This code is contributed by susmitakundugoaldanga.
```

## JavaScript 描述语言

```javascript
<script>

// Javascript program for the above approach

// Function to find duplicate characters
// in string without using any additional
// data structure
function findDuplicate(str, N)
{

    // Check if (i + 'a') is present
    // in str at least once or not.
    let first = 0;

    // Check if (i + 'a') is present
    // in str at least twice or not.
    let second = 0;

    // Iterate over the characters
    // of the string str
    for(let i = 0; i < N; i++)
    {

        // If str[i] has already occurred in str
        if ((first & (1 << (str[i].charCodeAt() -
                               'a'.charCodeAt()))) != 0)
        {

            // Set (str[i] - 'a')-th bit of second
            second = second | (1 << (str[i].charCodeAt() -
                                        'a'.charCodeAt()));
        }
        else
        {

            // Set (str[i] - 'a')-th bit of second
            first = first | (1 << (str[i].charCodeAt() -
                                      'a'.charCodeAt()));
        }
    }

    // Iterate over the range [0, 25]
    for(let i = 0; i < 26; i++)
    {

        // If i-th bit of both first
        // and second is Set
        if (((first & (1 << i)) &
            (second & (1 << i))) != 0)
        {
            document.write(String.fromCharCode(
                i + 'a'.charCodeAt()) + " ");
        }
    }
}

// Driver code
let str = "geeksforgeeks";
let N = str.length;

findDuplicate(str, N);

// This code is contributed by divyesh072019

</script>
```

`Output`:

```text
e g k s
```

时间复杂度: `O(N)`
空间复杂度: `O(1)`