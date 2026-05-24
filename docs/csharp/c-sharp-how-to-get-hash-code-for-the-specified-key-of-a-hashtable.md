# C# |如何获取哈希表指定键的哈希代码

> 原文:[https://www . geeksforgeeks . org/c-sharp-如何获取哈希表指定键的哈希代码/](https://www.geeksforgeeks.org/c-sharp-how-to-get-hash-code-for-the-specified-key-of-a-hashtable/)

**哈希表。GetHash(Object)** 方法用于获取一个 [Hashtable](https://www.geeksforgeeks.org/c-hashtable-class/) 对象的指定键的 hashcode。该方法继承自[对象类](https://www.geeksforgeeks.org/c-object-class/)。

**语法:**

```cs
protected virtual int GetHash(Object Key);

```

**异常:**如果*键*为空，该方法将给出*空引用异常*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# Program to illustrate the 
// Hashtable.GetHash(Object) method
using System;
using System.Collections;

// Inheriting Hashtable as 
// Hashtable.GetHash(Object) 
// method is protected method
class HashCode : Hashtable {

    // Main Method
    static void Main(string[] args)
    {

        // creating object for HashCode as
        // to access protected methods we
        // have to create object for the 
        // derived class
        HashCode h = new HashCode();

        // Add Elements into Hashtable
        h.Add("1001", "Parek Shetty");
        h.Add("1002", "Deshmuk Narayan");
        h.Add("1003", "Ratan Kaalikaran");

        ICollection Key = h.Keys;

        foreach(string val in Key)
        {

            // printing Hashtable
            Console.Write(val + " : " + h[val]);
            Console.Write("\n");

            // printing hashcode with keys
            int hcode = h.GetHash(val);

            Console.Write(val + " : " + hcode);
            Console.Write("\n");
        }
    }
}
```

**Output:**

```cs
1002 : Deshmuk Narayan
1002 : 985757554
1001 : Parek Shetty
1001 : -1708895167
1003 : Ratan Kaalikaran
1003 : -1892225314

```

**例 2:**

```cs
// C# Program to illustrate the 
// Hashtable.GetHash(Object) method
using System;
using System.Collections;

class HashCode : Hashtable {

    // Main Method
    static void Main(string[] args)
    {
        HashCode h = new HashCode();

        // Adding elements
        h.Add('A', "Pritam Devadhya");
        h.Add('B', "Arjun Balachi");
        h.Add('C', "Timanad Panigrahi");

        ICollection Key = h.Keys;

        int hcode = h.GetHash('C');

        Console.Write("HashCode: " + hcode);
    }
}
```

**Output:**

```cs
HashCode: 4390979

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . hashtable . gethash？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.hashtable.gethash?view=netframework-4.7.2)