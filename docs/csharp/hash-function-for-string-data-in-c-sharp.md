# c# 中字符串数据的哈希函数

> 原文:[https://www . geesforgeks . org/hash-function-for-string-data-in-c-sharp/](https://www.geeksforgeeks.org/hash-function-for-string-data-in-c-sharp/)

**问题:**用 C# 编写代码来散列一个键数组，并用它们的散列代码显示它们。

*答案:* Hashtable 是一种广泛使用的数据结构，用于存储用其哈希代码索引的值(即键)。哈希代码是哈希函数的结果，用作存储密钥的索引值。如果两个不同的密钥散列到相同的值，这种情况被称为*冲突*，一个好的散列函数可以最大限度地减少冲突。

**问题:**如何选择适合数据的哈希函数？

*回答:*如果你的数据由整数组成，那么最简单的散列函数是返回键的除法的余数和表的大小。保持表的大小为质数是很重要的。但是可以编写更复杂的函数来避免冲突。如果您的数据由字符串组成，那么您可以将字母表中的所有 ASCII 值相加，并用表格的大小对总和取模(下面的代码描述了相同的情况)。

**例 1:**

```cs
// C# Program to create a Hash 
// Function for String data
using System;

class Geeks {

    // Main Method
    public static void Main(String []args)
    {

        // Declaring the an string array
        string[] values = new string[50];
        string str;

        // Values of the keys stored
        string[] keys = new string[] {"Alphabets", 
              "Roman", "Numbers", "Alphanumeric", 
                                  "Tallypoints"};

        int hashCode;

        for (int k = 0; k < 5; k++) {

            str = keys[k];

            // calling HashFunction
            hashCode = HashFunction(str, values);

            // Storing keys at their hashcode's index
            values[hashCode] = str;
        }

        // Displaying Hashcodes along with key values
        for (int k = 0; k < (values.GetUpperBound(0)); k++) {

            if (values[k] != null)
                Console.WriteLine(k + " " + values[k]);
        }
    }

    // Defining the hash function
    static int HashFunction(string s, string[] array)
    {
        int total = 0;
        char[] c;
        c = s.ToCharArray();

        // Summing up all the ASCII values 
        // of each alphabet in the string
        for (int k = 0; k <= c.GetUpperBound(0); k++)
            total += (int)c[k];

        return total % array.GetUpperBound(0);
    }
}
```

**输出:**

```cs
11 Tallypoints
16 Alphanumeric
19 Roman
34 Alphabets
46 Numbers

```

**例 2:**

```cs
// C# Program to create a Hash 
// Function for String data
using System;

class Geeks {

    // Main Method
    public static void Main(String []args)
    {

        // Declaring the an string array
        string[] values = new string[50];
        string str;

        // Values of the keys stored
        string[] keys = new string[] {"C", "C++", 
                 "Java", "Python", "C#", "HTML"};

        int hashCode;

        for (int k = 0; k < 5; k++) {

            str = keys[k];
            hashCode = HashFunction2(str, values);

            // Storing keys at their hashcode's index
            values[hashCode] = str;
        }

        // Displaying Hashcodes along with key values
        for (int k = 0; k < (values.GetUpperBound(0)); k++) {

            if (values[k] != null)
                Console.WriteLine(k + " " + values[k]);
        }
    }

    // Defining the hash function
    static int HashFunction2(string s, string[] array)
    {
        long total = 0;
        char[] c;
        c = s.ToCharArray();

        // Horner's rule for generating a polynomial 
        // of 11 using ASCII values of the characters
        for (int k = 0; k <= c.GetUpperBound(0); k++)

            total += 11 * total + (int)c[k];

        total = total % array.GetUpperBound(0);

        if (total < 0)
            total += array.GetUpperBound(0);

        return (int)total;
    }
}
```

**输出:**

```cs
6 C#
15 C++
18 C
19 Python
28 Java

```

**解释:**在*散列函数*中，我们将参数作为要散列的字符串传递，字符串数据“*的值为*。方法 *[ToCharArray](https://www.geeksforgeeks.org/c-tochararray-method/)* 将字符串转换为字符数组，然后我们从字符数组的开始到结束开始一个 for 循环。在 for 循环中，我们计算数组中每个字符的 ASCII 值的总和。方法 [GetUpperBound](https://www.geeksforgeeks.org/c-finding-the-index-of-last-element-in-the-array/) 返回数组最高索引的值。然后哈希函数返回总和除以数组上限的模(在本例中为 49，因为*字符串[]值=新字符串[50]* )。而在*中有函数 2* ，我们传递相同的参数，但是这个函数不太可能有冲突。除了这里我们用*霍纳法则*计算 11 的多项式函数外，其他都基本相同。