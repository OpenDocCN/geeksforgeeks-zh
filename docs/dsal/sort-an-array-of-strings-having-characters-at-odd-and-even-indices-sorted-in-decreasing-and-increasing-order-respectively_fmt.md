# 对具有奇数和偶数索引字符的字符串数组进行排序，这些字符分别按降序和升序排序

> 原文: [https://www.geeksforgeeks.org/sort-an-array-of-strings-having-characters-at-odd-and-even-indices-sorted-in-decreasing-and-increasing-order-respectively/](https://www.geeksforgeeks.org/sort-an-array-of-strings-having-characters-at-odd-and-even-indices-sorted-in-decreasing-and-increasing-order-respectively/)

给定一个由 `N` 个字符串组成的数组 `arr[]`，任务是首先对数组中的每个字符串分别按降序和升序对字符串的奇数和偶数索引处的字符进行排序，然后对修改后的数组进行排序。

**示例:**

> **输入:** `arr[] = {“ball”, “bat”, “boy”}`
> **输出:** `albl atb byo`
> **解释:**
> `S[0]=“ball”` 转换为 `“albl”`
> `S[1]=“bat”` 转换为 `“ATB”`
> `S[2]=“boy”` 转换为 `“byo”`
> 修改后数组的排序顺序为: `albl atb byo`。

> **输入:** `arr[]= {“geeks”, “gfg”, “hello”, “world”}`
> **输出:** `dwell eohll esekg fgg`

**方法:** 给定的问题可以通过遍历字符串的给定数组 `arr[]` 来解决，对于每个字符串，首先对字符串进行排序，然后重新排列每个字符串，使得 **偶数索引** 处的字符按升序排列，而 **奇数索引** 处的字符按降序排列。最后，以升序对新的字符串数组进行排序。按照以下步骤解决问题:

*   遍历给定的字符串数组 `arr[]`，并对每个字符串执行以下步骤:
    *   按字母顺序排列字符串 `arr[i]`。
    *   初始化一个变量，比如说 `temp` 为 `""`，存储结果字符串。
    *   遍历字符串 `arr[i]` 为字符串的半长 `arr[i]` 并存储从字符串的开始和结束到字符串 `temp` 的 `i` 索引。
    *   如果字符串的大小为奇数，则在变量 `temp` 的末尾添加字符串 `arr[i]` 的 **中间** 字符。
    *   完成上述步骤后，将数组 `arr[i]` 的 `i` 索引处的字符串更新为字符串 `temp`。
*   完成上述步骤后，按升序对新的字符串数组进行排序并打印字符串数组 `arr[]`。

下面是上述方法的实现。

## C++

```cpp
// C++ program for the above approach

#include <bits/stdc++.h>
using namespace std;

// Function to sort even indices in
// ascending order and odd indices in
// descending order and sort the array
// of strings in ascending order
void sortString(string S[], int N)
{
    // Traverse array of strings
    for (int i = 0; i < N; i++) {

        // Sort string in ascending order
        sort(S[i].begin(), S[i].end());

        // Length of string
        int n = S[i].size();

        string temp = "";

        // Traverse the string
        for (int j = 0; j < n / 2; j++) {
            temp += S[i][j];
            temp += S[i][n - j - 1];
        }

        // If length of string is odd
        if (n & 1)
            temp += S[i][n / 2];

        S[i] = temp;
    }

    // Sort array of strings
    sort(S, S + N);

    // Print array of strings
    for (int i = 0; i < N; i++) {
        cout << S[i] << " ";
    }
}

// Driver Code
int main()
{
    string arr[] = { "ball", "bat", "boy" };
    int N = sizeof(arr) / sizeof(arr[0]);
    sortString(arr, N);

    return 0;
}
```

## Java

```java
// Java program for the above approach
import java.util.*;

class GFG{

static String sortString(String inputString)
{

    // Convert input string to char array
    char tempArray[] = inputString.toCharArray();

    // Sort tempArray
    Arrays.sort(tempArray);

    // Return new sorted string
    return new String(tempArray);
}

// Function to sort even indices in
// ascending order and odd indices in
// descending order and sort the array
// of Strings in ascending order
static void sortString(String S[], int N)
{

    // Traverse array of Strings
    for(int i = 0; i < N; i++)
    {

        // Sort String in ascending order
        S[i] = sortString(S[i]);

        // Length of String
        int n = S[i].length();

        String temp = "";

        // Traverse the String
        for(int j = 0; j < n / 2; j++)
        {
            temp += S[i].charAt(j);
            temp += S[i].charAt(n - j - 1);
        }

        // If length of String is odd
        if (n %2== 1)
            temp += S[i].charAt(n / 2);

        S[i] = temp;
    }

    // Sort array of Strings
    Arrays.sort(S);

    // Print array of Strings
    for(int i = 0; i < N; i++)
    {
        System.out.print(S[i] + " ");
    }
}

// Driver Code
public static void main(String[] args)
{
    String arr[] = { "ball", "bat", "boy" };
    int N = arr.length;

    sortString(arr, N);
}
}

// This code is contributed by Amit Katiyar
```

## Python 3

```python
# Python3 program for the above approach

# Function to sort even indices in
# ascending order and odd indices in
# descending order and sort the array
# of strings in ascending order
def sortString(S, N):

    # Traverse array of strings
    for i in range(N):

        # Sort string in ascending order
        S[i] = ''.join(sorted(S[i]))

        # Length of string
        n = len(S[i])

        temp = ""

        # Traverse the string
        for j in range(n // 2):
            temp += S[i][j]
            temp += S[i][n - j - 1]

        # If length of string is odd
        if (n & 1):
            temp += S[i][n // 2]

        S[i] = temp

    # Sort array of strings
    S.sort()

    # Print array of strings
    for i in range(N):
        print(S[i], end = " ")

# Driver Code
if __name__ == '__main__':

    arr = ["ball", "bat", "boy"]
    N = len(arr)

    sortString(arr, N)

# This code is contributed by ipg2016107
```

## C#

```csharp
// C# program for the above approach
using System;

public class GFG{

static String sortString(String inputString)
{

    // Convert input string to char array
    char []tempArray = inputString.ToCharArray();

    // Sort tempArray
    Array.Sort(tempArray);

    // Return new sorted string
    return new String(tempArray);
}

// Function to sort even indices in
// ascending order and odd indices in
// descending order and sort the array
// of Strings in ascending order
static void sortString(String []S, int N)
{

    // Traverse array of Strings
    for(int i = 0; i < N; i++)
    {

        // Sort String in ascending order
        S[i] = sortString(S[i]);

        // Length of String
        int n = S[i].Length;

        String temp = "";

        // Traverse the String
        for(int j = 0; j < n / 2; j++)
        {
            temp += S[i][j];
            temp += S[i][n - j - 1];
        }

        // If length of String is odd
        if (n %2== 1)
            temp += S[i][n / 2];

        S[i] = temp;
    }

    // Sort array of Strings
    Array.Sort(S);

    // Print array of Strings
    for(int i = 0; i < N; i++)
    {
        Console.Write(S[i] + " ");
    }
}

// Driver Code
public static void Main(String[] args)
{
    String []arr = { "ball", "bat", "boy" };
    int N = arr.Length;

    sortString(arr, N);
}
}

// This code is contributed by Amit Katiyar
```

**Output:**

```
albl atb byo
```

时间复杂度: `O(N*log N)`
辅助空间: `O(1)`