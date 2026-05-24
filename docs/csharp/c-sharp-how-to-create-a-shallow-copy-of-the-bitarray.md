# C# |如何创建 BitArray 的浅拷贝

> 原文:[https://www . geesforgeks . org/c-sharp-如何创建一个浅拷贝的 bitarray/](https://www.geeksforgeeks.org/c-sharp-how-to-create-a-shallow-copy-of-the-bitarray/)

**BitArray。克隆方法**用于创建数组的浅拷贝。此方法仅复制集合的元素，无论它们是引用类型还是值类型，但不复制引用所引用的对象。
**语法:**

```cs
public object Clone ();
```

**示例 1:** 这里我们创建一个类型字节的数组。然后声明一个 BitArray 类型的对象 *B1* ，并使用之前创建的字节数组初始化它。声明另一个 BitArray 类型的对象 *B2* ，该对象将用于存储 *B1* 的克隆。说明书 *B1。克隆*返回 *B1* 的浅拷贝，类型为*系统。收藏*。因此，在将其存储到 *B2* 对象之前，请将其显式转换为 BitArray。最后，显示克隆的 BitArray。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to demonstrate the
// BitArray.Clone Method
using System;
using System.Collections;

class GFG {

    static void Main(string[] args)
    {
        // Declaring a byte array
        byte[] ByteArray = new byte[] {1, 3};

        // Declaring a BitArray object
        // Initializing to the byte array
        BitArray B1 = new BitArray(ByteArray);

        // Declaring a new BitArray object
        BitArray B2 = new BitArray(4);

        // Using the BitArray.Clone method
        B2 = (BitArray)B1.Clone();

        // Displaying the length of the BitArray
        Console.WriteLine("Length of B2: {0}", B2.Length);

        Console.WriteLine("\nB2 Contains:");

        // To display the values
        // of BitArray object B2
        foreach(Object item in B2)
        {
            Console.WriteLine(item);
        }

    }
}
```

**Output:** 

```cs
Length of B2: 16

B2 Contains:
True
False
False
False
False
False
False
False
True
True
False
False
False
False
False
False
```

**示例 2:** 浅拷贝只拷贝 BitArray 的内容，不拷贝对象引用，对 B2 所做的任何更改只会更新 B2 的那些更改，而不会更新 B1 的那些更改。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# Program to show changes in clone
// don't affect the original BitArray
using System;
using System.Collections;

class GFG {

    static void Main(string[] args)
    {
        // Declaring a bool array
        bool[] BooleanArray = new bool[] {true,
                          false, true, false };

        // Declaring an object B1 of BitArray
        // Initialising with the bool array
        BitArray B1 = new BitArray(BooleanArray);

        int i;

        // Declaring object B2 of BitArray
        BitArray B2 = new BitArray(4);

        // Using the BitArray.Clone method
        B2 = (BitArray)B1.Clone();

        i = 4;

        // Displaying elements of B2
        Console.WriteLine("B2 Before Making any changes:");

        foreach(Object item in B2)
        {
            if (i <= 0)
            {
                Console.WriteLine();
                i = 6;
            }
            i--;
            Console.Write("{0, 4} ", item);
        }

        // Updating elements of B2
        // at index 0 and 1
        B2[0] = false;
        B2[1] = true;

        i = 4;

        // Displaying elements
        // of B2 after updating
        Console.WriteLine("\n\nB2 After changes:");

        foreach(Object item in B2)
        {
            if (i <= 0)
            {
                Console.WriteLine();
                i = 6;
            }
            i--;
            Console.Write("{0, 4} ", item);
        }

        // Displaying elements of B1
        Console.WriteLine("\n\nB1 After Changes:");

        i = 4;

        foreach(Object item in B1)
        {
            if (i <= 0)
            {
                Console.WriteLine();
                i = 6;
            }
            i--;
            Console.Write("{0, 4} ", item);
        }

    }
}
```

**Output:** 

```cs
B2 Before Making any changes:
True False True False 

B2 After changes:
False True True False 

B1 After Changes:
True False True False
```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . bitarray . clone？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray.clone?view=netframework-4.7.2)