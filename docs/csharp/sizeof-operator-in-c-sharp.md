# c# 中 sizeof()运算符

> 原文:[https://www.geeksforgeeks.org/sizeof-operator-in-c-sharp/](https://www.geeksforgeeks.org/sizeof-operator-in-c-sharp/)

sizeof()运算符用于以字节为单位获取数据类型的大小。它不会返回变量或实例的大小。它的返回类型总是 int。

**语法:**

```cs
int sizeof(type);
```

**示例:**

```cs
Input : sizeof(byte);
Output : 1

Input : sizeof(int);
Output : 4

```

```cs
// C# program to illustrate the 
// sizeof() operator
using System;
using System.IO;
using System.Text;

namespace IncludeHelp
{
    class Test
    {
        // Main Method 
        static void Main(string[] args)
        {
            Console.WriteLine("sizeof(char)     : {0}", sizeof(char));
            Console.WriteLine("sizeof(byte)     : {0}", sizeof(byte));
            Console.WriteLine("sizeof(sbyte)    : {0}", sizeof(sbyte));
            Console.WriteLine("sizeof(float)    : {0}", sizeof(float));
            Console.WriteLine("sizeof(ushort)   : {0}", sizeof(ushort));
            Console.WriteLine("sizeof(double)   : {0}", sizeof(double));
            Console.WriteLine("sizeof(int)      : {0}", sizeof(int));
            Console.WriteLine("sizeof(bool)     : {0}", sizeof(bool));
            Console.WriteLine("sizeof(short)    : {0}", sizeof(short));

        }
    }
}
```

**输出:**

```cs
sizeof(char)     : 2
sizeof(byte)     : 1
sizeof(sbyte)    : 1
sizeof(float)    : 4
sizeof(ushort)   : 2
sizeof(double)   : 8
sizeof(int)      : 4
sizeof(bool)     : 1
sizeof(short)    : 2

```