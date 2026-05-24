# C# |字符串。索引( )方法|设置–1

> 原文:[https://www . geesforgeks . org/c-sharp-string-indexof-method-set-1/](https://www.geeksforgeeks.org/c-sharp-string-indexof-method-set-1/)

在 C# 中， ***IndexOf()*** 法是一种 **[串](https://www.geeksforgeeks.org/c-string/)** 法。此方法用于在字符串的当前实例中查找指定字符或字符串的第一个匹配项的从零开始的索引。如果找不到字符或字符串，该方法返回-1。这个方法可以通过传递不同的参数来重载。

*   **弦。IndexOf(char x)**
*   **弦。IndexOf(char x，int start1)**
*   **弦。IndexOf(char x，int start1，int start2)**
*   **弦。索引 Of(字符串 s1)**
*   **弦。IndexOf(字符串 s1，int start1)**
*   **弦。IndexOf(字符串 s1，int start1，int start2)**
*   **弦。IndexOf(字符串 s1，int start1，int start2，StringComparison cType)**
*   **弦。IndexOf(字符串 s1，int start1，StringComparison cType)**
*   **字符串。IndexOf(string s1，string comparison cttype)**

#### 字符串。IndexOf(char x)方法

此方法返回字符串中指定字符的第一个匹配项的从零开始的索引。如果找不到这样的字符，则返回-1。

**语法:**

```cs
public int IndexOf(char x)

```

*   **参数:**该方法取*系统类型的参数 **char x** 。指定要搜索的字符的字符*。
*   **返回类型:**该方法的返回类型为*系统。Int32* 。

**示例:**在下面的代码中，用户想要知道字符‘F’在指定字符串“GeeksForGeeks”中的索引，因此，该方法返回各自的结果，主要是字符‘F’的第一次出现。同样在第二种情况下，字符“C”不存在，所以它只返回-1。

```cs
// C# program to illustrate the 
// String.IndexOf(char x) method
using System;
namespace ConsoleApplication1 {

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        string str = "GeeksForGeeks";

        // Finding the index of character 
        // which is present in string and
        // this will show the value 5
        int index1 = str.IndexOf('F');

        Console.WriteLine("The Index Value of character 'F' is " + index1);

        // Now finding the index of that character which
        //  is not even present with the string
        int index2 = str.IndexOf('C');

        // As expected, this will output value -1
        Console.WriteLine("The Index Value of character 'C' is " + index2);
    }
}
}
```

**输出:**

```cs
The Index Value of character 'F' is 5
The Index Value of character 'C' is -1
```

#### 字符串。IndexOf(char x，int start1)方法

此方法返回字符串中指定字符的第一个匹配项的从零开始的索引。但是，对该字符的搜索将从指定位置开始，如果没有找到，它将返回-1。

**语法:**

```cs
public int IndexOf(char x, int start1)

```

*   **参数:**该方法取两个参数，即*系统类型的 **char x** 。指定要搜索的字符的字符*和**开始 1** 类型的*系统。Int32* 以整数值的形式指定开始搜索的位置。
*   **返回类型:**该方法的返回类型为*系统。Int32* 。
*   **异常:**如果*开始 1* 小于 0(零)或大于字符串长度，此方法可以给出**argumentout of range Exception**。

**示例:**在下面的代码中，用户想要知道指定字符串“HelloGeeks”中字符“H”的索引，因此，该方法返回字符“H”的相应索引。然而，如果**开始 1** 大于 1，那么很明显返回-1。

```cs
// C# program to illustrate the 
// String.IndexOf(char x, int start1) method
using System;
namespace ConsoleApplication2{

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        string str = "HelloGeeks";

        // Finding the index of character
        // which is present in string
        // this will show the value 0
        int index1 = str.IndexOf('H', 0);

        Console.WriteLine("The Index Value of character 'H' "+
                          "with start index 0 is " + index1);

        // Now finding the index of character 
        // 'H' with starting position greater
        // than index position of 'H'
        int index2 = str.IndexOf('H', 5);

        // As expected, this will output value -1
        Console.WriteLine("The Index Value of character 'H' is " + index2);
    }
}
}
```

**输出:**

```cs
The Index Value of character 'H' with start index 0 is 0
The Index Value of character 'H' is -1
```

#### 字符串。IndexOf(char x，int start1，int start2)方法

此方法返回字符串中指定字符的第一个匹配项的从零开始的索引。但是，对该字符的搜索将从指定位置*开始 1* 直到指定位置即*开始 2* 为止，如果没有找到，则返回-1。

**语法:**

```cs
public int IndexOf(char x, int start1, int start2)

```

*   **参数:**该方法取三个参数，即*系统类型的 **char x** 。指定要搜索的字符的字符*，开始 1 类型的*系统。Int32* 以整数值的形式指定开始搜索的位置，以及**开始 2** 类型的*系统。Int32* 指定停止搜索的结束位置。
*   **返回类型:**该方法的返回类型为*系统。Int32* 。
*   **异常:**如果 *start1 或 start2 为负*或 *start1 大于当前字符串的长度*或 *start2 大于当前字符串的长度减去 start1* ，此方法可给出**argumentout of range 异常**。

**示例:**在下面的代码中，用户想知道指定字符串“我的生活我的规则”中字符“R”的索引，因此，该方法返回字符“R”的索引值。同样，对于开始 1 > 1 和开始 2 < 8 的情况，它再次返回-1，因为它没有找到任何字符。

```cs
// C# program to illustrate the
// String.IndexOf(char x, int start1,
//  int start2) method
using System;
namespace ConsoleApplication3 {

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        string str = "My Life My Rules";

        int index1 = str.IndexOf('R', 2, 14);

        // Here starting index is < Index value of 'R'
        // Also ending index is > Index of 'R'
        // Hence It is obvious to return 11
        Console.WriteLine("Index Value of 'R' with start"+ 
                          " Index =2 and end Index = 15 is " + index1);

        // Now here starting index is chosen right
        // However ending position is < index of 'R'
        // Surely it will return -1
        int index2 = str.IndexOf('R', 1, 8);

        Console.WriteLine("Index Value of 'R' with start"+
                          " Index = 1 and end Index = 8 is " + index2);
    }
}
}
```

**输出:**

```cs
Index Value of 'R' with start Index =2 and end Index = 15 is 11
Index Value of 'R' with start Index = 1 and end Index = 8 is -1

```

#### 字符串。IndexOf(字符串 s1)方法

此方法返回字符串中指定子字符串的第一个匹配项的从零开始的索引。如果没有找到这样的字符串，那么它将返回-1，与字符的情况相同。

**语法:**

```cs
public int IndexOf(string s1)

```

*   **参数:**该方法取*系统类型的参数 **s1** 。字符串*指定要搜索的子字符串。
*   **返回类型:**该方法的返回类型为*系统。Int32* 。如果找到该字符串，则为 s1 的从零开始的索引位置，否则为-1。如果 s1 是字符串。空，返回值为 0。
*   **异常:**如果 *s1* 为空，这个方法可以给出 **ArgumentNullException** 。

**示例:**在下面的代码中，已知字符串“How”存在于主字符串中，因此它将简单地返回其第一个字符的索引值。但是，在下一种情况下，没有名为“Chair”的子字符串，所以它只返回-1。

```cs
// C# program to illustrate the
// String.IndexOf(string  s1) method
using System;
namespace ConsoleApplication4 {

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        string str = "Hello Friends....How are you...";

        int i = str.IndexOf("How");

        // As this string is present in the 
        // main string then it will obviously
        //  output the value as 17
        Console.WriteLine("First value Index of 'How' is " + i);

        // now the following string is not present
        // So as per the rules, it will return -1
        int i1 = str.IndexOf("Chair");

        // As this string is present in 
        // the main string then it will 
        // obviously output the value as -1
        Console.WriteLine("First value Index of 'Chair' is " + i1);
    }
}
}
```

**输出:**

```cs
First value Index of 'How' is 17
First value Index of 'Chair' is -1
```