# C# |检查两个数组对象是否相等

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-two-bitarray-objects-equal/](https://www.geeksforgeeks.org/c-sharp-check-if-two-bitarray-objects-are-equal/)

从 Object 类继承的 **Equals(Object)方法**用于检查指定的 [BitArray](https://www.geeksforgeeks.org/c-bitarray-class/) 对象是否等于另一个 [BitArray](https://www.geeksforgeeks.org/c-bitarray-class/) 对象。

**语法:**

```cs
public virtual bool Equals (object obj);
```

这里， *obj* 是要与当前对象进行比较的对象。

**返回值:**如果指定对象等于当前对象，则该方法返回*真*，否则返回*假*。

以下程序说明了上述方法的使用:

**例 1:**

```cs
// C# code to if specified 
// BitArray object is equal 
// to the current object
using System; 
using System.Collections; 

class GFG { 

    // Driver code 
    public static void Main() 
    { 

        // Creating a BitArray 
        BitArray myBitArr1 = new BitArray(4); 

        // Creating a BitArray 
        BitArray myBitArr2 = new BitArray(4); 

        // Initializing values in myBitArr1 
        myBitArr1[0] = false; 
        myBitArr1[1] = false; 
        myBitArr1[2] = true; 
        myBitArr1[3] = true; 

        // Initializing values in myBitArr2 
        myBitArr2[0] = false; 
        myBitArr2[2] = false; 
        myBitArr2[1] = true; 
        myBitArr2[3] = true; 

       // using Equals(Object) method 
       // to check if myBitArr1 is 
       // equal to myBitArr2 or not
       Console.WriteLine(myBitArr1.Equals(myBitArr2));         
    } 
} 
```

**输出:**

```cs
False

```

**例 2:**

```cs
// C# code to if specified
// BitArray object is equal
// to the current object
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr1 = new BitArray(4);

        // Creating a BitArray
        BitArray myBitArr2 = new BitArray(4);

        // Initializing values in myBitArr1
        myBitArr1[0] = false;
        myBitArr1[1] = false;
        myBitArr1[2] = true;
        myBitArr1[3] = true;

        // Initializing values in myBitArr2
        myBitArr2[0] = false;
        myBitArr2[2] = false;
        myBitArr2[1] = true;
        myBitArr2[3] = true;

        // using Equals(Object) method
        // to check if myBitArr1 is
        // equal to myBitArr2 or not
        Console.WriteLine(myBitArr1.Equals(myBitArr2));

        // Creating a BitArray
        BitArray myBitArr3 = new BitArray(4);

        // assigning myBitArr2 to myBitArr3
        myBitArr3 = myBitArr2;

        // using Equals(Object) method
        // to check if myBitArr2 is
        // equal to myBitArr3 or not
        Console.WriteLine(myBitArr2.Equals(myBitArr3));

    }
}
```

**输出:**

```cs
False
True

```

**注意:**如果当前实例是引用类型， *Equals(对象)*方法检查引用是否相等。