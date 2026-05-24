# C# 中装箱和拆箱的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-boxing-and-unboxing-in-c-sharp/](https://www.geeksforgeeks.org/difference-between-boxing-and-unboxing-in-c-sharp/)

`打拳拆箱`是 C# 中的一个重要概念。C# Type 系统包含三种数据类型：`值类型(int、char 等)`、`引用类型(object)` 和 `指针类型`。基本上，它将值类型转换为引用类型，反之亦然。装箱和取消装箱实现了类型系统的统一视图，其中任何类型的值都可以被视为对象。

| 装箱 | 拆箱 |
| --- | --- |
| 它将值类型转换为对象类型。 | 它将对象类型转换为值类型。 |
| 装箱是一个隐含的转换过程。 | 取消装箱是显式的转换过程。 |
| 这里，存储在堆栈上的值被复制到存储在堆内存中的对象上。 | 这里，存储在堆内存中的对象被复制到存储在堆栈中的值。 |
| **示例：** | **示例：** |
| ```cs<br>// C# program to illustrate Boxing<br>using System;<br><br>public class GFG {<br>    static public void Main()<br>    {<br>        int val = 2019;<br><br>        // Boxing<br>        object o = val;<br><br>        // Change the value of val<br>        val = 2000;<br><br>        Console.WriteLine("Value type of val is {0}", val);<br>        Console.WriteLine("Object type of val is {0}", o);<br>    }<br>}<br>``` | ```cs<br>// C# program to illustrate Unboxing<br>using System;<br><br>public class GFG {<br>    static public void Main()<br>    {<br>        int val = 2019;<br><br>        // Boxing<br>        object o = val;<br><br>        // Unboxing<br>        int x = (int)o;<br><br>        Console.WriteLine("Value of o is {0}", o);<br>        Console.WriteLine("Value of x is {0}", x);<br>    }<br>}<br>``` |
| **输出：** | **输出：** |
| ```cs<br>Value type of val is 2000<br>Object type of val is 2019<br>``` | ```cs<br>Value of o is 2019<br>Value of x is 2019<br>``` |