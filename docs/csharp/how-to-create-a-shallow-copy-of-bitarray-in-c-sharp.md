# 如何在 C# 中创建 BitArray 的浅拷贝

> 原文:[https://www . geeksforgeeks . org/如何创建 c-sharp 中 bitarray 的浅拷贝/](https://www.geeksforgeeks.org/how-to-create-a-shallow-copy-of-bitarray-in-c-sharp/)

**BitArray。克隆()方法**用于创建指定 [BitArray](https://www.geeksforgeeks.org/c-sharp-bitarray-class/) 的浅拷贝。集合的浅层副本仅复制集合的元素，而不考虑引用类型或值类型。但是它不会复制引用所引用的对象。新集合中的引用指向与原始集合中的引用指向的对象相同的对象。

**语法:**

```cs
public object Clone ();
```

**示例:**

```cs
// C# code to illustrate the use 
// of BitArray.Clone Method
using System;
using System.Collections;

public class GFG {

    // Main Method
    public static void Main(String[] args)
    {

        // Creating an empty BitArray
        BitArray bit1 = new BitArray(4);

        // Initializing values in bit1
        bit1[0] = false;
        bit1[1] = false;
        bit1[2] = true;
        bit1[3] = true;

        // Displaying the list
        Console.WriteLine("Elements of Original BitArray: \n");

        // calling function
        Result(bit1);

        // using Clone() method
        BitArray bit2 = (BitArray)bit1.Clone();

        // Displaying the Cloned BitArray
        Console.WriteLine("\nElements of Cloned BitArray: \n");

        // calling function
        Result(bit2);

        // checking for the equality  
        // of References bit1 and bit2 
        Console.WriteLine("\nReference Equals: {0}", 
          Object.ReferenceEquals(bit1, bit2)); 

    }

// method to display the values
public static void Result(IEnumerable bit) 
{ 
    // This method prints all the 
    // elements in the BitArray. 
    foreach(Object obj in bit) 
        Console.WriteLine(obj); 
} 
}
```

**Output:**

```cs
Elements of Original BitArray: 

False
False
True
True

Elements of Cloned BitArray: 

False
False
True
True

Reference Equals: False

```