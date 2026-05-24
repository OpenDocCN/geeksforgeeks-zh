# C# `Random.NextBytes()` 方法

> 原文：[https://www.geeksforgeeks.org/c-sharp-random-nextbytes-method/](https://www.geeksforgeeks.org/c-sharp-random-nextbytes-method/)

`Random` 类的 `NextBytes(Byte[])` 方法用于用随机数填充指定字节数组的元素。此方法将字节数组作为参数，并用随机数填充它。

## 语法

```cs
public virtual void NextBytes (byte[] buffer);
```

这里，`buffer` 是包含随机数的字节数组。

## 异常

如果 `buffer` 为 `null`，此方法将给出 `ArgumentNullException`。

## 示例

下面的程序说明了 `NextBytes()` 方法的使用：

### 例 1

```cs
// C# program to illustrate the
// use of Random.NextBytes Method
using System;

class GFG {

    // Driver code
    public static void Main()
    {
        // Instantiate random number generator
        Random rand = new Random();

        // Instantiate an array of byte
        Byte[] b = new Byte[10];

        rand.NextBytes(b);

        // Print random numbers in the byte array
        Console.WriteLine("Printing random numbers"+
                          " in the byte array");

        for (int i = 0; i < 10; i++)
            Console.WriteLine("{0} -> {1}", i, b[i]);
    }
}
```

**输出：**

```cs
Printing random numbers in the byte array
0 -> 63
1 -> 166
2 -> 5
3 -> 212
4 -> 114
5 -> 94
6 -> 161
7 -> 4
8 -> 226
9 -> 46
```

### 例 2

```cs
// C# program to illustrate the
// use of Random.NextBytes Method
using System;

class GFG {

    // Driver code
    public static void Main()
    {
        // Instantiate random number generator
        Random rand = new Random();

        // Instantiate an array of byte
        Byte[] b = new Byte[10];

        rand.NextBytes(b);

        // Print random numbers in the byte array
        Console.WriteLine("Printing random numbers"+
                          " in the byte array");

        foreach(byte byteValue in b)
            Console.WriteLine("{0}", byteValue);
    }
}
```

**输出：**

```cs
Printing random numbers in the byte array
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.random.nextbytes?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.random.nextbytes?view=netframework-4.7.2)