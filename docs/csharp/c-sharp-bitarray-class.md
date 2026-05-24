# 【t0 c# \位数组类】T1

> 原文:[https://www.geeksforgeeks.org/c-sharp-bitarray-class/](https://www.geeksforgeeks.org/c-sharp-bitarray-class/)

**BitArray** 类管理一个紧凑的位值数组，这些位值被表示为布尔值，其中 true 表示该位在上是**，即 **1** ，false 表示该位在**下是**，即 **0** 。这个类包含在 ***系统中。集合*** 命名空间。**

**BitArray 类的属性:**

*   BitArray 类是一个集合类，其中的容量始终与计数相同。
*   通过增加 ***长度*** 属性，元素被添加到数组中。
*   通过减少 ***长度*** 属性来删除元素。
*   可以使用整数索引访问此集合中的元素。此集合中的索引从零开始。

#### 构造器

| 构造器 | 描述 |
| **位数组(位数组)** | 初始化 BitArray 类的新实例，该实例包含从指定 BitArray 复制的位值。 |
| **位数组(布尔[])t1** | 初始化 BitArray 类的新实例，该实例包含从指定的布尔值数组中复制的位值。 |
| **位数组(字节[]** | 初始化 BitArray 类的新实例，该实例包含从指定的字节数组复制的位值。 |
| **位数组(Int32)** | 初始化 BitArray 类的新实例，该实例可以保存指定数量的位值，这些值最初设置为 false。 |
| **位数组(Int32，布尔)** | 初始化 BitArray 类的新实例，该实例可以保存指定数量的位值，这些位值最初设置为指定的值。 |
| **位数组(Int32[]个)** | 初始化 BitArray 类的新实例，该实例包含从指定的 32 位整数数组中复制的位值。 |

**示例:**

```cs
// C# code to create a BitArray
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray
        BitArray myBitArr = new BitArray(5);

        myBitArr[0] = true;
        myBitArr[1] = true;
        myBitArr[2] = false;
        myBitArr[3] = true;
        myBitArr[4] = false;

        // To get the value of index at index 2
        Console.WriteLine(myBitArr.Get(2));

        // To get the value of index at index 3
        Console.WriteLine(myBitArr.Get(3));
    }
}
```

**输出:**

```cs
False
True

```

#### 性能

| 财产 | 描述 |
| **[计数](https://www.geeksforgeeks.org/c-number-of-elements-contained-in-the-bitarray/)** | 获取 BitArray 中包含的元素数量。 |
| **[【isreadonly】](https://www.geeksforgeeks.org/c-check-if-the-bitarray-is-read-only/)** | 获取一个值，该值指示 BitArray 是否为只读。 |
| **[同步](https://www.geeksforgeeks.org/c-check-if-the-bitarray-is-synchronized-thread-safe/)** | 获取一个值，该值指示对 BitArray 的访问是否同步(线程安全)。 |
| **[项【国际 32】](https://www.geeksforgeeks.org/c-gets-or-sets-the-value-of-the-bit-at-a-specific-position-in-the-bitarray/)** | 获取或设置 BitArray 中特定位置的位的值。 |
| **[长度](https://www.geeksforgeeks.org/c-get-or-set-the-number-of-elements-in-the-bitarray/)** | 获取或设置数组中的元素数。 |
| 同步根 | 获取一个对象，该对象可用于同步对 BitArray 的访问。 |

**示例:**

```cs
// C# program to illustrate the 
// BitArray Class Properties
using System; 
using System.Collections; 

class GFG { 

    // Driver code 
    public static void Main() 
    { 

        // Creating a BitArray 
        BitArray myBitArr = new BitArray(new byte[] { 0, 0, 0, 1 }); 

        // -------- IsReadOnly Property --------

        // Checking if the BitArray is read-only 
        Console.WriteLine(myBitArr.IsReadOnly); 

        // -------- Count Property --------

        // To get the number of elements 
        // contained in the BitArray 
        Console.WriteLine(myBitArr.Count); 

    } 
} 
```

**输出:**

```cs
False
32

```

#### 方法

| 方法 | 描述 |
| **[和(BitArray)](https://www.geeksforgeeks.org/c-bitwise-and-between-the-elements-of-bitarray/)** | 在当前 BitArray 对象的元素和指定数组中的相应元素之间执行按位“与”运算。当前的 BitArray 对象将被修改以存储按位“与”运算的结果。 |
| **T1】克隆()T3】** | 创建位图的浅拷贝。 |
| **[CopyTo(Array，Int32)](https://www.geeksforgeeks.org/c-copying-bitarray-elements-to-an-array/)** | 从目标数组的指定索引开始，将整个数组复制到兼容的一维数组。 |
| **[等于(对象)](https://www.geeksforgeeks.org/c-check-if-two-bitarray-objects-are-equal/)** | 确定指定的对象是否等于当前对象。 |
| **[Get(Int32)](https://www.geeksforgeeks.org/c-get-value-of-the-bit-at-a-specific-position-in-bitarray/)** | 获取数组中特定位置的位的值。 |
| **[【get 分子()](https://www.geeksforgeeks.org/c-enumerator-that-iterates-through-the-bitarray/)** | 返回遍历 BitArray 的枚举数。 |
| **[左移(Int32)](https://www.geeksforgeeks.org/bitarray-leftshift-method-in-c-sharp-with-examples/)** | 它用于将位阵列的位向左移动一个位置，并在移动的位置上添加零。 |
| **GetHashCode（）** | 用作默认哈希函数。 |
| gettype() | 获取当前实例的类型。 |
| **MemberWiseCrone()** | 创建当前对象的浅拷贝。 |
| **[不是()](https://www.geeksforgeeks.org/c-inverting-all-bit-values-in-bitarray/)** | 反转当前 BitArray 中的所有位值，以便设置为 true 的元素更改为 false，设置为 false 的元素更改为 true。 |
| [**右移(Int32)**](https://www.geeksforgeeks.org/bitarray-rightshift-method-in-c-sharp-with-examples/) | 它用于将位阵列的位向右移动一个位置，并在移动的位置上添加零。 |
| **[或(BitArray)](https://www.geeksforgeeks.org/c-bitwise-or-operation-between-the-elements-of-bitarray/)** | 在当前 BitArray 对象的元素和指定数组中的相应元素之间执行按位“或”运算。当前 BitArray 对象将被修改以存储按位“或”运算的结果。 |
| **[集合(Int32，布尔)](https://www.geeksforgeeks.org/c-set-the-bit-at-a-specific-position-in-the-bitarray-to-the-specified-value/)** | 将 BitArray 中特定位置的位设置为指定值。 |
| **[集合全部（布尔值）](https://www.geeksforgeeks.org/c-set-all-bits-in-the-bitarray-to-the-specified-value/)** | 将 BitArray 中的所有位设置为指定值。 |
| **ToString()** | 返回表示当前对象的字符串。 |
| **[Xor(BitArray)](https://www.geeksforgeeks.org/c-bitwise-exclusive-or-operation-between-the-elements-of-bitarray/)** | 针对指定数组中的相应元素，在当前 BitArray 对象的元素之间执行按位异或运算。当前 BitArray 对象将被修改以存储按位异或运算的结果。 |

**例 1:**

```cs
// C# code to do bitwise
// OR between BitArray
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

        // function calling
        PrintValues(myBitArr1.Or(myBitArr2));
    }

    // Displaying the result
    public static void PrintValues(IEnumerable myList)
    {
        foreach(Object obj in myList)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**输出:**

```cs
False
True
True
True

```

**例 2:**

```cs
// C# code to set all bits in the
// BitArray to the specified value
using System;
using System.Collections;

class GFG {

    // Driver code
    public static void Main()
    {

        // Creating a BitArray myBitArr
        BitArray myBitArr = new BitArray(5);

        // Initializing all the bits in myBitArr
        myBitArr[0] = false;
        myBitArr[1] = true;
        myBitArr[2] = true;
        myBitArr[3] = false;
        myBitArr[4] = true;

        // Printing the values in myBitArr
        Console.WriteLine("Initially the bits are as : ");

        PrintIndexAndValues(myBitArr);

        // Setting all bits to false
        myBitArr.SetAll(false);

        // Printing the values in myBitArr
        // It should display all the bits as false
        Console.WriteLine("Finally the bits are as : ");

        PrintIndexAndValues(myBitArr);
    }

    // Function to display bits
    public static void PrintIndexAndValues(IEnumerable myArr)
    {
        foreach(Object obj in myArr)
        {
            Console.WriteLine(obj);
        }
    }
}
```

**输出:**

```cs
Initially the bits are as : 
False
True
True
False
True
Finally the bits are as : 
False
False
False
False
False

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . collections . bitarray？视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.collections.bitarray?view=netframework-4.7.2)