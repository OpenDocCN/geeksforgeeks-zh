# 如何在 C# 中将 ASCII 字符转换为字节？

> 原文:[https://www . geesforgeks . org/how-convert-ascii-char-to-byte in-c-sharp/](https://www.geeksforgeeks.org/how-to-convert-ascii-char-to-byte-in-c-sharp/)

给定一个字符，任务是将这个 ASCII 字符转换成 C# 中的一个字节。

**示例:**

```cs
Input: chr = 'a'
Output: 97

Input: chr = 'H'
Output: 72

```

**方法 1:天真方法**

> ***第一步:**获得人物。*
> 
> ***步骤 2:** 使用字节结构*转换字符
> 
> ```cs
> byte b = (byte) chr;
> 
> ```
> 
> **步骤 3:** 返回或对字节执行操作

下面是上述方法的实现:

## C#

```cs
// C# program to convert 
// ascii char to byte.

using System;

public class GFG{

    static public void Main ()
    { 
        char ch = 'G'; 

        // Creating byte 
        byte byt; 

        // converting character into byte 
        byt = (byte)ch; 

        // printing character with byte value
        Console.WriteLine("Byte of char \'" + ch + "\' : " + byt);

    } 
}
```

**输出:**

```cs
Byte of char 'G' : 71

```

**方法二:使用**[**ToByte**](https://www.geeksforgeeks.org/c-sharp-convert-tobytestring-iformatprovider-method/)**()方法:**此方法为 Convert 类方法。它用于将其他基本数据类型转换为字节数据类型。

**语法:**

```cs
byte byt = Convert.ToByte(char); 

```

下面是上述方法的实现:

## C#

```cs
// C# program to convert 
// ascii char to byte.

using System;

public class GFG{

    static public void Main ()
    { 
        char ch = 'G'; 

        // Creating byte 
        byte byt; 

        // converting character into byte 
        // using Convert.ToByte() method
        byt = Convert.ToByte(ch); 

        // printing character with byte value
        Console.WriteLine("Byte of char \'" +
                    ch + "\' : " + byt);

    } 
}
```

**输出:**

```cs
Byte of char 'G' : 71

```

**方法三:使用** [**获取字节**](https://www.geeksforgeeks.org/c-sharp-bitconverter-class/)**()【0】方法:**将编码为。 ASCII 。 GetBytes() 方法用于 接受一个字符串作为参数，得到字节数组。因此 GetBytes()[0]用于获取将字符转换为字符串后的字节。

**语法:**

```cs
byte byt = Encoding.ASCII.GetBytes(string str)[0]; 

```

> **第一步:**获取角色。
> 
> **第二步:**使用[**to string(**](https://www.geeksforgeeks.org/c-sharp-char-tostring-method/)**)****方法** **将字符转换为字符串。**
> 
> **第三步:**使用**获取字节****()【0】方法**将字符串转换为字节，并将转换后的字符串存储到字节中。
> 
> **步骤 4:** 返回或对字节执行操作。

下面是上述方法的实现:

## C#

```cs
// C# program to convert 
// ascii char to byte.

using System;
using System.Text;

public class GFG{

    static public void Main ()
    { 
        char ch = 'G'; 

        // convert to string
        // using the ToString() method
        string str = ch.ToString();

        // Creating byte 
        byte byt; 

        // converting character into byte 
        // using GetBytes() method
        byt = Encoding.ASCII.GetBytes(str)[0]; 

        // printing character with byte value
        Console.WriteLine("Byte of char \'" +
                          ch + "\' : " + byt);

    } 
}
```

**输出:**

```cs
Byte of char 'G' : 71

```