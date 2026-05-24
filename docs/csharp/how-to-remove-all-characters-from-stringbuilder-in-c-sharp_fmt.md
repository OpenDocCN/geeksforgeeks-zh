# 如何在 C# 中移除 StringBuilder 中的所有字符

> 原文: [https://www.geeksforgeeks.org/how-to-remove-all-characters-from-stringbuilder-in-c-sharp/](https://www.geeksforgeeks.org/how-to-remove-all-characters-from-stringbuilder-in-c-sharp/)

## 语法

`StringBuilder.Clear` 方法用于从当前字符串生成器实例中移除所有字符。

```cs
public System.Text.StringBuilder Clear ();
```

它返回一个长度为零的 `StringBuilder` 对象。

## 注意

*   `Clear` 是一个便捷方法，其功能等同于将当前实例的 `Length` 属性设置为 0。
*   调用 `Clear` 方法不会修改当前实例的 `Capacity` 或 `MaxCapacity` 属性。

## 例

```cs
// C# program to demonstrate
// the Clear() Method
using System;
using System.Text;

class GFG {

// Main Method
    public static void Main(String[] args)
    {
        // Creating a StringBuilder object
        StringBuilder sb1 = new StringBuilder("GeeksforGeeks");

        // printing the length of "GeeksforGeeks"
        Console.WriteLine("The String is: {0} \nTotal characters -- {1}",
                         sb1.ToString(), sb1.Length);

        // using the method
        sb1.Clear();

        // printing the length of "GeeksforGeeks"
        Console.WriteLine("The String is: {0} \nTotal characters -- {1}",
                         sb1.ToString(), sb1.Length);

        sb1.Append("This  is C# Tutorials.");

        // printing the length of "GeeksforGeeks"
        Console.WriteLine("The String is: {0} \nTotal characters -- {1}",
                         sb1.ToString(), sb1.Length);
    }
}
```

## 输出

```cs
The String is: GeeksforGeeks 
Total characters -- 13
The String is:  
Total characters -- 0
The String is: This  is C# Tutorials. 
Total characters -- 22
```

## 参考

*   [https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.clear?view=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder.clear?view=netframework-4.7.2)