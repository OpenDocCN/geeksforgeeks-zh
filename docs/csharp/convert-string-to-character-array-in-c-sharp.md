# 在 C# 中将字符串转换为字符数组

> 原文:[https://www . geesforgeks . org/convert-string-to-character-array-in-c-sharp/](https://www.geeksforgeeks.org/convert-string-to-character-array-in-c-sharp/)

给定一个[字符串](https://www.geeksforgeeks.org/c-sharp-string/)，任务是将这个字符串转换成 C# 中的字符数组。

**示例:**

```cs
Input:  string 
Output:  [s, t, r, i, n, g]

Input:  GeeksForGeeks
Output:  [G, e, e, k, s, F, o, r, G, e, e, k, s]  

```

**方法 1:天真方法**

> **第一步:**获取字符串。
> 
> **步骤 2:** 创建一个与字符串长度相同的字符数组。
> 
> **步骤 3:** 遍历字符串，将字符串第 I 个索引处的字符复制到数组的第 I 个索引处。
> 
> **第四步:**返回或对字符数组执行操作。

下面是上述方法的实现:

## C#

```cs
// C# program to Convert a string 
// to a Character array 
// using Naive Approach 

using System;

public class GFG{

    static public void Main ()
    { 
        string str = "GeeksForGeeks"; 

        // Creating array of string length 
        char[] ch = new char[str.Length]; 

        // Copy character by character into array 
        for (int i = 0; i < str.Length; i++) { 
            ch[i] = str[i]; 
        } 

        // Printing content of array 
        foreach  (char c in ch) { 
            Console.WriteLine(c); 
        } 
    } 
}
```

**输出:**

```cs
G
e
e
k
s
F
o
r
G
e
e
k
s

```

**方法二:** 使用[T5【to chararray](https://www.geeksforgeeks.org/c-sharp-tochararray-method/)**()**方法

> **第一步:**获取字符串。
> 
> **步骤 2:** 创建一个与字符串长度相同的字符数组。
> 
> **第三步:**存储 toCharArray()方法返回的数组。
> 
> **第四步:**返回或对字符数组进行运算。

## C#

```cs
// C# program to Convert a string 
// to a Character array 
// using ToCharArray method 

using System;

public class GFG{

    static public void Main ()
    { 
        string str = "GeeksForGeeks"; 

        // Creating array of string length 
        // Copy character by character into array 
        char[] ch = str.ToCharArray();

        // Printing content of array 
        foreach  (char c in ch) { 
            Console.WriteLine(c); 
        } 
    } 
}
```

**输出:**

```cs
G
e
e
k
s
F
o
r
G
e
e
k
s

```