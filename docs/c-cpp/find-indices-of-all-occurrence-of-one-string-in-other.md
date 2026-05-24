# 查找一个字符串在其他字符串中所有出现的索引

> 原文:[https://www . geesforgeks . org/find-indexs-of-all-occurrence-in-other-string/](https://www.geeksforgeeks.org/find-indices-of-all-occurrence-of-one-string-in-other/)

给定两个字符串，str1 和 str2，任务是打印 str1 中 str2 出现的索引(考虑，从 0 开始的索引)。如果没有出现这样的索引，则打印“无”。

**示例:**

```cpp
Input : GeeksforGeeks
        Geeks
Output : 0 8

Input : GFG
        g
Output : NONE
```

一个**简单的解决方案**是逐个检查给定字符串的所有子字符串。如果子串匹配，打印其索引。

## C++

```cpp
// C++ program to find indices of all
// occurrences of one string in other.
#include <iostream>
using namespace std;
void printIndex(string str, string s)
{

    bool flag = false;
    for (int i = 0; i < str.length(); i++) {
        if (str.substr(i, s.length()) == s) {
            cout << i << " ";
            flag = true;
        }
    }

    if (flag == false)
        cout << "NONE";
}
int main()
{
    string str1 = "GeeksforGeeks";
    string str2 = "Geeks";
    printIndex(str1, str2);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
// Java program to find indices of all
// occurrences of one String in other.
class GFG {

    static void printIndex(String str, String s)
    {

        boolean flag = false;
        for (int i = 0; i < str.length() - s.length() + 1; i++) {
            if (str.substring(i, i + s.length()).equals(s)) {
                System.out.print(i + " ");
                flag = true;
            }
        }

        if (flag == false) {
            System.out.println("NONE");
        }
    }

    // Driver code
    public static void main(String[] args)
    {
        String str1 = "GeeksforGeeks";
        String str2 = "Geeks";
        printIndex(str1, str2);
    }
}

// This code is contributed by Rajput-JI
```

## 蟒蛇 3

```cpp
# Python program to find indices of all
# occurrences of one String in other.
def printIndex(str, s):

    flag = False;
    for i in range(len(str)):
        if (str[i:i + len(s)] == s):

            print( i, end =" ");
            flag = True;

    if (flag == False):
        print("NONE");

# Driver code       
str1 = "GeeksforGeeks";
str2 = "Geeks";
printIndex(str1, str2);

# This code contributed by PrinciRaj1992
```

## C#

```cpp
// C# program to find indices of all
// occurrences of one String in other.
using System;

class GFG {

    static void printIndex(String str, String s)
    {

        bool flag = false;
        for (int i = 0; i < str.Length - s.Length + 1; i++) {
            if (str.Substring(i,
                              s.Length)
                    .Equals(s)) {
                Console.Write(i + " ");
                flag = true;
            }
        }

        if (flag == false) {
            Console.WriteLine("NONE");
        }
    }

    // Driver code
    public static void Main(String[] args)
    {
        String str1 = "GeeksforGeeks";
        String str2 = "Geeks";
        printIndex(str1, str2);
    }
}

// This code is contributed by 29AjayKumar
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```cpp
<?php
// PHP program to find indices of all
// occurrences of one string in other.
function printIndex($str, $s)
{
    $flag = false;
    for ($i = 0; $i < strlen($str); $i++)
    {
        if (substr($str,$i, strlen($s)) == $s)
        {
            echo $i . " ";
            $flag = true;
        }
    }

    if ($flag == false)
        echo "NONE";
}

// Driver Code
$str1 = "GeeksforGeeks";
$str2 = "Geeks";
printIndex($str1, $str2);

// This code is contributed by mits
?>
```

## java 描述语言

```cpp
<script>
      // JavaScript program to find indices of all
      // occurrences of one String in other.
      function printIndex(str, s) {
        var flag = false;
        for (var i = 0; i < str.length - s.length + 1; i++) {
          if (str.substring(i, s.length + i) == s) {
            document.write(i + " ");
            flag = true;
          }
        }

        if (flag === false) {
          document.write("NONE");
        }
      }

      // Driver code
      var str1 = "GeeksforGeeks";
      var str2 = "Geeks";
      printIndex(str1, str2);
</script>
```

**Output:** 

```cpp
0 8
```

**时间复杂度:** O(n * n)

一个**高效的解决方案**是 [KMP 字符串匹配算法](https://www.geeksforgeeks.org/searching-for-patterns-set-2-kmp-algorithm/)。