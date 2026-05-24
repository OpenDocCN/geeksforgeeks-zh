# C# | Byte.GetHashCode()方法

> 原文: [`https://www.geeksforgeeks.org/c-sharp-byte-gethashcode-method/`](https://www.geeksforgeeks.org/c-sharp-byte-gethashcode-method/)

此方法用于返回给定字节的哈希代码。

### 语法:
```cs
public override int GetHashCode ();
```

### 返回值:
该方法返回当前字节的哈希码。

下面的程序说明了 `Byte.GetHashCode()` 方法的使用:

### 示例 1:
```cs
// C# program to demonstrate
// Byte.GetHashCode Method
using System;

class GFG {

// Main Method
    public static void Main()
    {

// Declaring and initializing val
        long val = 83935;

// converting long array into bytes
        byte[] bytes = BitConverter.GetBytes(val);

// getting hashcode
        // using GetHashCode() method
        for (int i = 0; i < bytes.Length; i++) {

// getting hash code of a single byte
            int j = bytes[i].GetHashCode();

Console.WriteLine("Hashcode: {0}", j);
        }
    }
}
```

### Output:
```cs
Hashcode: 223
Hashcode: 71
Hashcode: 1
Hashcode: 0
Hashcode: 0
Hashcode: 0
Hashcode: 0
Hashcode: 0
```

### 示例 2:
```cs
// C# program to demonstrate
// Byte.GetHashCode Method
using System;

class GFG {

// Main Method
    public static void Main()
    {

check((long)8543, "long");
        check((int)8543, "int");
        check((byte)85, "byte");
    }

// Defining the check method
    public static void check(long val, string name)
    {

// converting long array into bytes
        byte[] bytes = BitConverter.GetBytes(val);

// getting hashcode
        // using GetHashCode() method
        Console.Write(name + " hashcode:- ");
        for (int i = 0; i < bytes.Length; i++) {

// getting hash code of a single byte
            int j = bytes[i].GetHashCode();
            Console.Write("{0} ", j);
        }
        Console.WriteLine("");
    }

// Defining the check method
    public static void check(int val, string name)
    {

// converting long array into bytes
        byte[] bytes = BitConverter.GetBytes(val);

// getting hashcode
        // using GetHashCode() method
        Console.Write(name + " Hashcode: ");
        for (int i = 0; i < bytes.Length; i++) {

// getting hash code of a single byte
            int j = bytes[i].GetHashCode();
            Console.Write("{0} ", j);
        }
        Console.WriteLine("");
    }

// Defining the check method
    public static void check(byte val, string name)
    {

// converting long array into bytes
        byte[] bytes = BitConverter.GetBytes(val);

// getting hashcode
        // using GetHashCode() method
        Console.Write(name + " hashcode:- ");
        for (int i = 0; i < bytes.Length; i++) {

// getting hash code of a single byte
            int j = bytes[i].GetHashCode();
            Console.Write("{0} ", j);
        }
        Console.WriteLine("");
    }
}
```

### Output:
```cs
long hashcode:- 95 33 0 0 0 0 0 0 
int Hashcode: 95 33 0 0 
byte hashcode:- 85 0
```

### 参考:
*   [`https://docs.microsoft.com/en-us/dotnet/api/system.byte.gethashcode?view=netframework-4.7.2`](https://docs.microsoft.com/en-us/dotnet/api/system.byte.gethashcode?view=netframework-4.7.2)