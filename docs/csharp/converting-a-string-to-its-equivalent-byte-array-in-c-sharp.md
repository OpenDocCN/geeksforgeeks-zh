# 在 C# 中将字符串转换为其等效字节数组

> 原文:[https://www . geeksforgeeks . org/将字符串转换为其等效的 c-sharp 字节数组/](https://www.geeksforgeeks.org/converting-a-string-to-its-equivalent-byte-array-in-c-sharp/)

给定一个[字符串](https://www.geeksforgeeks.org/c-sharp-string/)，任务是将这个字符串转换成 C# 中的字节数组。

**示例:**

```cs
Input: aA
Output: [97, 65 ]

Input: Hello
Output: [ 72, 101, 108, 108, 111 ]

```

### **方法 1:**

**使用**[**ToByte**](https://www.geeksforgeeks.org/c-sharp-convert-tobytestring-iformatprovider-method/)**()方法:**此方法为 Convert 类方法。它用于将其他基本数据类型转换为字节数据类型。

**语法:**

```cs
byte byt = Convert.ToByte(char); 

```

> **第一步:**获取字符串。
> 
> **步骤 2:** 创建一个与字符串长度相同的字节数组。
> 
> **步骤 3:** 遍历字符串，使用**T**T5【oByte()方法将每个字符转换为字节，并将所有字节存储到字节数组中。
> 
> **步骤 4:** 返回或对字节数组执行操作。

下面是上述方法的实现:

## C#

```cs
// C# program to convert a given
// string to its equivalent byte[]

using System;

public class GFG{

    static public void Main ()
    { 
        string str = "GeeksForGeeks"; 

        // Creating byte array of string length 
        byte[] byt = new byte[str.Length]; 

        // converting each character into byte 
        // and store it
        for (int i = 0; i < str.Length; i++) { 
            byt[i] = Convert.ToByte(str[i]); 
        } 

        // printing characters with byte values
        for(int i =0; i<byt.Length; i++)
        {
            Console.WriteLine("Byte of char \'" + str[i] + "\' : " + byt[i]);
        }

    } 
}
```

**输出:**

```cs
Byte of char 'G' : 71
Byte of char 'e' : 101
Byte of char 'e' : 101
Byte of char 'k' : 107
Byte of char 's' : 115
Byte of char 'F' : 70
Byte of char 'o' : 111
Byte of char 'r' : 114
Byte of char 'G' : 71
Byte of char 'e' : 101
Byte of char 'e' : 101
Byte of char 'k' : 107
Byte of char 's' : 115

```

### **方法二:**

**使用** [**获取字节**](https://www.geeksforgeeks.org/c-sharp-bitconverter-class/) **()方法:**将编码为。 ASCII 。 GetBytes() 方法用于 接受一个字符串作为参数，得到字节数组。

**语法:**

```cs
byte[] byte_array = Encoding.ASCII.GetBytes(string str); 

```

> **第一步:**获取字符串。
> 
> **步骤 2:** 创建一个空字节数组。
> 
> **第三步:**使用 **GetBytes** **()方法**将字符串转换为字节[]并将所有转换字符串存储到字节数组中。
> 
> **步骤 4:** 返回或对字节数组执行操作。

## C#

```cs
// C# program to convert a given
// string to its equivalent byte[]

using System;
using System.Text;

public class GFG{

    static public void Main ()
    { 
        string str = "GeeksForGeeks"; 

        // Creating byte array of string length 
        byte[] byt; 

        // converting each character into byte 
        // and store it
        byt = Encoding.ASCII.GetBytes(str);

        // printing characters with byte values
        for(int i =0; i<byt.Length; i++)
        {
            Console.WriteLine("Byte of char \'" + str[i] + "\' : " + byt[i]);
        }

    } 
}
```

**输出:**

```cs
Byte of char 'G' : 71
Byte of char 'e' : 101
Byte of char 'e' : 101
Byte of char 'k' : 107
Byte of char 's' : 115
Byte of char 'F' : 70
Byte of char 'o' : 111
Byte of char 'r' : 114
Byte of char 'G' : 71
Byte of char 'e' : 101
Byte of char 'e' : 101
Byte of char 'k' : 107
Byte of char 's' : 115

```