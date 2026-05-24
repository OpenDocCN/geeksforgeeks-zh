# C# 8.0 中的空合并赋值运算符

> 原文：[https://www.geeksforgeeks.org/null-coalescing-assignment-operator-in-c-sharp-8-0/](https://www.geeksforgeeks.org/null-coalescing-assignment-operator-in-c-sharp-8-0/)

C# 8.0 引入了一个新的运算符，称为空值合并赋值运算符（`??=`）。仅当左侧操作数的值为空时，此运算符用于将其右侧操作数的值赋给左侧操作数。如果左侧操作数的计算结果为非空，则该运算符不计算其右侧操作数。

## 语法

```cs
p ??= q
```

这里，`p` 是左操作数，`q` 是右操作数。`??=` 运算符。如果 `p` 的值为空，那么 `??=` 运算符在 `p` 中指定 `q` 的值。或者，如果 `p` 的值非空，则它不计算 `q`。

## 要点

*   `??=` 运算符的左操作数必须是变量、属性或索引器元素。
*   它是右联想的。
*   你不能重载 `??=` 运算符。
*   你被允许将 `??=` 运算符与引用类型和值类型一起使用。

## 示例

```cs
// C# program to illustrate how to use 
// ??= operator with value types and 
// reference types
using System;

namespace example {

class GFG {

    static void Main(string[] args)
    {

        // Reference types
        string item_1 = null;
        string item_2 = null;
        string item_4 = "GeeksforGeeks";
        string item_5 = "GFG";

        // Using ??= operator
        item_1 = item_1 ??= item_4;
        string item_6 = item_2 ??= item_5;

        Console.WriteLine("Value of item_1 is: {0}\n"+
           "Value of item_6 is:{1}", item_1, item_6);

        // Value types
        int? ele_1 = null;

        GFG obj = new GFG();

        // Using ??= operator assigns
        // the value of ele_1
        // And also you are allowed to 
        // use method with ??= operator
        ele_1 = ele_1 ??= obj.Add(10, 30);
        Console.WriteLine("Value of ele_1 is {0}", ele_1);
    }

    // Method
    public int Add(int a, int b)
    {
        int result = a + b;
        return result;
    }
}
}
```

**输出：**

```cs
Value of item_1 is: GeeksforGeeks
Value of item_6 is:GFG
Value of ele_1 is 40
```

*   借助 `??=` 运算符，你可以消除许多冗余的“if-else”条件，使你的代码更紧凑、可读性更强。如下例所示：

```cs
// C# program to illustrate how to use
// ??= operator to remove if statements
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Nullable variable
        int? element = null;

        // Checking the element is null or not
        if (element is null) {

            // Assign a new value to the element
            // Using ??= operator
            int? new_element = element ??= 400;
            Console.WriteLine("Element is null. "+
              "So the new element is: {0}", new_element);
        }
    }
}
}
```

**输出：**

```cs
Element is null. So the new element is: 400
```

```cs
// C# program to illustrate how to use
// ??= operator to remove if statements
using System;

namespace example {

class Program {
    static void Main(string[] args)
    {
        // Nullable variable
        int? element = null;

        // Using ??= operator
        // Assign values to the null variable
        element ??= 400;
        Console.WriteLine("Element is: {0}", element);
    }
}
}
```

**输出：**

```cs
Element is: 400
```

*   你也可以像嵌套链一样使用 `??=` 运算符。这使你的代码更具可读性。

```cs
// C# program to illustrate 
// how to nest ??= operator
using System;

namespace example {

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Nullable variables
        int? ele1 = null;
        int? ele2 = null;
        int? ele3 = 45;

        // Using Nested ??= operator
        int? result = ele1 ??= ele2 ??= ele3;

        Console.WriteLine("Element is: {0}", result);
    }
}
}
```

**输出：**

```cs
Element is: 45
```