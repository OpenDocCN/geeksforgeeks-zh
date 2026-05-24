# C# |标识符

> 原文:[https://www.geeksforgeeks.org/c-sharp-identifiers/](https://www.geeksforgeeks.org/c-sharp-identifiers/)

在编程语言中，标识符用于识别目的。或者换句话说，标识符是程序组件的用户定义名称。在 C# 中，标识符可以是类名、方法名、变量名或标签。
**例:**

```cs
public class GFG {
    static public void Main () 
    {
          int x;
    }
}
```

这里，上述示例中存在的标识符总数为 3，这些标识符的名称为:

*   **GFG:** 班级名称
*   **主要:**方法名称
*   **x:** 变量名

**在 C# 中定义标识符的规则:**
定义有效的 C# 标识符有一定的有效规则。这些规则应该被遵守，否则，我们会得到一个编译时错误。

*   标识符唯一允许的字符是所有字母数字字符(**【A-Z】**、**【A-Z】**、**【0-9】**)、“ **_** ”(下划线)。例如，“geek@”不是有效的 C# 标识符，因为它包含“@”特殊字符。
*   标识符不应以数字([0-9])开头。例如，“123 极客”在 C# 中不是有效的标识符。
*   标识符不应包含空格。

*   标识符不允许用作[关键字](https://www.geeksforgeeks.org/c-keywords/)，除非它们包含@作为前缀。例如: **@as** 是有效标识符，而“ **as** 不是因为它是关键字。
*   C# 标识符允许 Unicode 字符。
*   C# 标识符区分大小写。
*   C# 标识符不能超过 512 个字符。
*   标识符的名称中不包含两个连续的下划线，因为这类标识符用于实现。

**例:**

## c sharp . c sharp . c sharp . c sharp

```cs
// Simple C# program to illustrate identifiers
using System;

class GFG {

    // Main Method
    static public void Main()
    {

        // variable
        int a = 10;
        int b = 39;
        int c;

        // simple addition
        c = a + b;
        Console.WriteLine("The sum of two number is: {0}", c);
    }
}
```

**输出:**

```cs
The sum of two number is: 49
```

下表显示了上例中的标识符和关键字:

<figure class="table">

| 关键词 | 标识符 |
| --- | --- |
| 使用 | GFG |
| 公众的 | 主要的 |
| 静电 | a |
| 空的 | b |
| （同 Internationalorganizations）国际组织 | c |

</figure>