# C# | CompareOrdinal()方法

> 原文:[https://www . geeksforgeeks . org/c-sharp-compare ordinal-method/](https://www.geeksforgeeks.org/c-sharp-compareordinal-method/)

在 C# 中 ***CompareOrdinal()*** 是一个字符串方法。此方法用于使用每个字符串或子字符串中相应 Char 对象的数值来比较两个指定的字符串对象或子字符串。这个方法可以通过传递不同的参数来重载。

*   字符串，字符串
*   比较部分(字符串，Int32，字符串，Int32，Int32)

#### 

字符串，字符串

该方法用于通过计算每个字符串中相应 Char 对象的数值来比较两个特定的**字符串对象**。

**语法:**

```cs
public static int CompareOrdinal(
    string strA, string strB)
```

*   **参数:**该方法接受两个参数 *strA* 和 *strB* 。StrA 是要比较的第一个字符串，strB 是要比较的第二个字符串。两个参数的类型都是**系统。弦**。
*   **返回值:**该方法返回类型为*系统的整数值。Int32* 。如果两个字符串相等，则返回 0。如果第一个字符串大于第二个字符串，则返回正数，否则返回负数。

**示例:**

```cs
Input: 
              string s1 = "GFG";    
              string s2 = "GFG"; 

              string.CompareOrdinal(s1, s2)
Output: 0

Input: 
              string s1 = "hello";    
              string s2 = "csharp"; 
              string.CompareOrdinal(s1, s2)

Output: 5

Input: 
              string s1 = "csharp";    
              string s2 = "mello";

              string.CompareOrdinal(s1, s2)

Output: -5

```

**程序:**说明 CompareOrdinal(字符串 strA，字符串 strB)方法。

```cs
// C# program to demonstrate the 
// CompareOrdinal(string strA, string strB)
using System;
class Geeks {

    // Main Method
    public static void Main(string[] args)
    {

        // strings to be compared
        string s1 = "GFG";    
        string s2 = "GFG"; 
        string s3 = "hello";
        string s4 = "csharp";

        // using CompareOrdinal(string strA, string strB)
        // method to compare displaying resultant value
        Console.WriteLine(string.CompareOrdinal(s1, s2));
        Console.WriteLine(string.CompareOrdinal(s1, s3));
        Console.WriteLine(string.CompareOrdinal(s3, s4));
    }
}
```

**Output:**

```cs
0
-33
5

```

#### 

比较部分(字符串，Int32，字符串，Int32，Int32)

此方法用于比较两个特定字符串对象的子字符串，方法是计算每个子字符串中相应 Char 对象的数值。

**语法:**

```cs
public static int CompareOrdinal(
    string strA,
    int indexA,
    string strB,
    int indexB,
    int length
)

```

**参数:**该方法取五个参数， *strA* 为第一个字符串对象，相似的 *strB* 为第二个字符串对象， *indexA* 为 strA 中子串的起始索引， *indexB* 为 strB 中子串的起始索引， *length* 为子串中要比较的最大字符数。strA 和 StrB 的类型为**系统。字符串**和索引 a、索引 b 和长度属于**系统类型。Int32** 。

**返回值:**该方法将返回一个类型为**系统的整数值。Int32** 。如果两个子字符串相等并且长度为零，则此方法将返回 0。如果 strA 中的子字符串大于 strB 中的子字符串，它将返回正值，否则返回负值。

**异常:**此方法会在三种情况下给出**argumentout of range Exception**:

*   如果 strA 不为空，并且索引大于 strA 的长度。
*   如果 indexA、indexB 或长度为负。
*   如果字符串不为空，并且索引大于字符串的长度。

**程序:**为了说明比较关系(字符串 strA，int indexA，字符串 strB，int indexB，int length):

```cs
// C# program to illustrate the 
// CompareOrdinal(String, Int32, 
// String, Int32, Int32) method
using System;

class GFG {

    // Main Method
    static public void Main ()
    {

        // strings to be compared
        string s1 = "GeeksforGeeks";    
        string s2 = "GforG";

        // starting index of substrings
        int sub1 = 5;
        int sub2 = 1;

        // length (5th parameter)
        int l1 = 3;

        // using CompareOrdinal(String, Int32, 
        // String, Int32, Int32) method and 
        // storing the result in variable res
        int res = string.CompareOrdinal(s1, sub1, s2, sub2, l1);

        // Displaying the result
        Console.WriteLine("The Result is: " + res);

    }
}
```

**Output:**

```cs
The Result is: 0

```

**参考文献:**

*   [https://msdn . Microsoft . com/en-us/library/af 26 w0 wa(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/af26w0wa(v=vs.110).aspx)*   [https://msdn . Microsoft . com/en-us/library/es 986 B3 k(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/es986b3k(v=vs.110).aspx)