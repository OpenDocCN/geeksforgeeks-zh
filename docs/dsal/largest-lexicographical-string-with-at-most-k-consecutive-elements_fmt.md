# 最多包含`K`个连续元素的最大的词典字符串

> 原文：[https://www.geeksforgeeks.org/largest-lexicographical-string-with-at-most-k-consecutive-elements/](https://www.geeksforgeeks.org/largest-lexicographical-string-with-at-most-k-consecutive-elements/)

给定字符串`S`，任务是通过重新排列或删除元素来查找最大不超过元素连续出现的`K`的词典字符串。

## 示例

> **输入**：`S = "baccc", K = 2`
>
> **输出**：`res = "ccbca"`
>
> **说明**：由于`K = 2`，最多可以连续放置 2 个相同字符。
>
> `'c'`的数量为 3。
>
> `'b'`的数量为 1。
>
> `'a'`的数量为 1。
>
> 由于必须打印最大的词典字符串，因此 ，答案是`"ccbca"`。
>
> **输入**：`S = "xxxxzaz", K = 3`
>
> **输出**：`res = "zzxxxax"`

## 方法

1.  生成一个大小为 26 的频率数组，其中使用（字符串中的一个字符`a`）选择索引`i`。

2.  初始化一个空字符串以存储相应的更改。

3.  对于`i = 25`到 0，请执行以下操作：

    *   如果索引`i`处的频率大于`k`，则将`i +'a'`附加`K`次。 将索引`i`处的频率降低`K`，找到下一个优先级最高的元素，然后附加到答案并将相应索引处的频率降低 1。

    *   如果索引`i`处的频率大于 0 但小于`k`，则将其频率附加`i + 'a'`。

    *   如果索引`i`处的频率为 0，则该索引不能用于生成元素，因此请检查下一个可能的最高优先级元素。

### C++

```cpp
// C++ code for the above approach
#include <bits/stdc++.h>
using namespace std;
#define ll long long int

// Function to find the
// largest lexicographical
// string with given constraints.
string getLargestString(string s,
                        ll k)
{

    // vector containing frequency
    // of each character.
    vector<int> frequency_array(26, 0);

    // assigning frequency to
    for (int i = 0;
         i < s.length(); i++) {

        frequency_array[s[i] - 'a']++;
    }

    // empty string of string class type
    string ans = "";

    // loop to iterate over
    // maximum priority first.
    for (int i = 25; i >= 0;) {

        // if frequency is greater than
        // or equal to k.
        if (frequency_array[i] > k) {

            // temporary variable to operate
            // in-place of k.
            int temp = k;
            string st(1, i + 'a');
            while (temp > 0) {

                // concatenating with the
                // resultant string ans.
                ans += st;
                temp--;
            }

            frequency_array[i] -= k;

            // handling k case by adjusting
            // with just smaller priority
            // element.
            int j = i - 1;
            while (frequency_array[j]
                       <= 0
                   && j >= 0) {
                j--;
            }

            // condition to verify if index
            // j does have frequency
            // greater than 0;
            if (frequency_array[j] > 0
                && j >= 0) {
                string str(1, j + 'a');
                ans += str;
                frequency_array[j] -= 1;
            }
            else {

                // if no such element is found
                // than string can not be
                // processed further.
                break;
            }
        }

        // if frequency is greater than 0
        // and less than k.
        else if (frequency_array[i] > 0) {

            // here we don't need to fix K
            // consecutive element criteria.
            int temp = frequency_array[i];
            frequency_array[i] -= temp;
            string st(1, i + 'a');
            while (temp > 0) {
                ans += st;
                temp--;
            }
        }

        // otherwise check for next
        // possible element.
        else {
            i--;
        }
    }
    return ans;
}

// Driver program
int main()
{
    string S = "xxxxzza";
    int k = 3;
    cout << getLargestString(S, k)
         << endl;
    return 0;
}
```

### Java

```java
// Java code for 
// the above approach
import java.util.*;
class GFG{

// Function to find the
// largest lexicographical
// String with given constraints.
static String getLargestString(String s,
                               int k)
{
  // Vector containing frequency
  // of each character.
  int []frequency_array = new int[26];

  // Assigning frequency 
  for (int i = 0;
           i < s.length(); i++) 
  {
    frequency_array[s.charAt(i) - 'a']++;
  }

  // Empty String of 
  // String class type
  String ans = "";

  // Loop to iterate over
  // maximum priority first.
  for (int i = 25; i >= 0😉 
  {
    // If frequency is greater than
    // or equal to k.
    if (frequency_array[i] > k) 
    {
      // Temporary variable to 
      // operate in-place of k.
      int temp = k;
      String st = String.valueOf((char)(i + 'a'));
      while (temp > 0) 
      {
        // Concatenating with the
        // resultant String ans.
        ans += st;
        temp--;
      }

      frequency_array[i] -= k;

      // Handling k case by adjusting
      // with just smaller priority
      // element.
      int j = i - 1;

      while (frequency_array[j] <= 0 && 
             j >= 0) 
      {
        j--;
      }

      // Condition to verify if index
      // j does have frequency
      // greater than 0;
      if (frequency_array[j] > 0 && 
          j >= 0) 
      {
        String str = String.valueOf((char)(j + 'a'));
        ans += str;
        frequency_array[j] -= 1;
      }
      else
      {
        // If no such element is found
        // than String can not be
        // processed further.
        break;
      }
    }

    // If frequency is greater than 0
    // and less than k.
    else if (frequency_array[i] > 0) 
    {
      // Here we don't need to fix K
      // consecutive element criteria.
      int temp = frequency_array[i];
      frequency_array[i] -= temp;
      String st = String.valueOf((char)(i + 'a'));

      while (temp > 0) 
      {
        ans += st;
        temp--;
      }
    }

    // Otherwise check for next
    // possible element.
    else
    {
      i--;
    }
  }
  return ans;
}

// Driver code
public static void main(String[] args)
{
  String S = "xxxxzza";
  int k = 3;
  System.out.print(getLargestString(S, k));
}
}

// This code is contributed by shikhasingrajput
```

## Python3

```py
# Python3 code for the above approach

# Function to find the
# largest lexicographical
# string with given constraints.
def getLargestString(s, k):
    # Vector containing frequency
    # of each character.
    frequency_array = [0] * 26

    # Assigning frequency to
    for i in range(len(s)):
        frequency_array[ord(s[i]) - ord('a')] += 1

    # Empty string of 
    # string class type
    ans = ""

    # Loop to iterate over
    # maximum priority first.
    i = 25
    while i >= 0:
        # If frequency is greater than
        # or equal to k.
        if (frequency_array[i] > k):
            # Temporary variable to 
            # operate in-place of k.
            temp = k
            st = chr(i + ord('a'))

            while (temp > 0):
                # concatenating with the
                # resultant string ans.
                ans += st
                temp -= 1

            frequency_array[i] -= k

            # Handling k case by adjusting
            # with just smaller priority
            # element.
            j = i - 1

            while (frequency_array[j] <= 0 and j >= 0):
                j -= 1

            # Condition to verify if index
            # j does have frequency
            # greater than 0;
            if (frequency_array[j] > 0 and j >= 0):
                str1 = chr(j + ord('a'))
                ans += str1
                frequency_array[j] -= 1
            else:
                # if no such element is found
                # than string can not be
                # processed further.
                break

        # If frequency is greater than 0
        # and less than k.
        elif (frequency_array[i] > 0):
            # Here we don't need to fix K
            # consecutive element criteria.
            temp = frequency_array[i]
            frequency_array[i] -= temp
            st = chr(i + ord('a'))
            while (temp > 0):
                ans += st
                temp -= 1

        # Otherwise check for next
        # possible element.
        else:
            i -= 1

    return ans

# Driver code
if __name__ == "__main__":
    S = "xxxxzza"
    k = 3
    print(getLargestString(S, k))

# This code is contributed by Chitranayal
```

## C#

```cs
// C# code for 
// the above approach
using System;
class GFG{

// Function to find the
// largest lexicographical
// String with given constraints.
static String getLargestString(String s, int k)
{
  // List containing frequency
  // of each character.
  int []frequency_array = new int[26];

  // Assigning frequency 
  for (int i = 0; i < s.Length; i++) 
  {
    frequency_array[s[i] - 'a']++;
  }

  // Empty String of 
  // String class type
  String ans = "";

  // Loop to iterate over
  // maximum priority first.
  for (int i = 25; i >= 0;) 
  {
    // If frequency is greater than
    // or equal to k.
    if (frequency_array[i] > k) 
    {
      // Temporary variable to 
      // operate in-place of k.
      int temp = k;
      String st = String.Join("", (char)(i + 'a'));

      while (temp > 0) 
      {
        // Concatenating with the
        // resultant String ans.
        ans += st;
        temp--;
      }

      frequency_array[i] -= k;

      // Handling k case by adjusting
      // with just smaller priority
      // element.
      int j = i - 1;

      while (frequency_array[j] <= 0 && j >= 0) 
      {
        j--;
      }

      // Condition to verify if index
      // j does have frequency
      // greater than 0;
      if (frequency_array[j] > 0 && j >= 0) 
      {
        String str = String.Join("", (char)(j + 'a'));
        ans += str;
        frequency_array[j] -= 1;
      }
      else
      {
        // If no such element is found
        // than String can not be
        // processed further.
        break;
      }
    }

    // If frequency is greater than 0
    // and less than k.
    else if (frequency_array[i] > 0) 
    {
      // Here we don't need to fix K
      // consecutive element criteria.
      int temp = frequency_array[i];
      frequency_array[i] -= temp;
      String st = String.Join("", (char)(i + 'a'));

      while (temp > 0) 
      {
        ans += st;
        temp--;
      }
    }

    // Otherwise check for next
    // possible element.
    else
    {
      i--;
    }
  }
  return ans;
}

// Driver code
public static void Main(String[] args)
{
  String S = "xxxxzza";
  int k = 3;
  Console.Write(getLargestString(S, k));
}
}

// This code is contributed by Princi Singh
```

### 输出

`zzxxxax`

### 时间复杂度

`O(n)`