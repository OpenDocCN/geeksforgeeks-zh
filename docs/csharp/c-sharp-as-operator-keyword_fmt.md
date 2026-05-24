# C# | as 运算符关键字

> 原文: [https://www.geeksforgeeks.org/c-sharp-as-operator-keyword/](https://www.geeksforgeeks.org/c-sharp-as-operator-keyword/)

在软件的开发中，类型转换是一件不可避免的事情。在许多情况下，开发人员需要将一个对象（类型）转换成另一个对象（类型），有时他/她可能会得到 `InvalidCastException`。所以，为了克服这类异常，C# 提供了 `as` 运算符关键字。

`as` 运算符用于执行兼容引用类型或可空类型之间的转换。当对象与给定类型兼容时，该运算符返回对象，如果无法转换，则返回空值，而不是引发异常。`as` 操作者的工作方式与 `is` 操作者非常相似，只是方式有所缩短。

## 语法

```cs
expression as type
```

上面的语法相当于下面的代码。但是表达式变量将只计算一次。

```cs
expression is type ? (type)expression : (type)null
```

这里，`is` 是运算符关键字。

### 注意

C# 中的 `as` 运算符关键字仅用于可空、引用和装箱转换。它不能执行只能通过使用强制转换表达式来执行的用户定义的转换。

## 示例 1

在下面的代码中，`str1` 包含一个字符串，该字符串被分配给 `object` 类型的变量 `obj1`。现在，这个 `obj1` 使用 `as` 运算符被转换为字符串，并将结果分配给字符串类型的变量 `str2`。如果转换成功，则返回结果，否则返回 `null`。这里，`if(str2 != null)` 用于检查结果是否为 `null`。对于 `List<string> mylist = obj1 as List<string>` 转换失败，返回空值。

```cs
// C# program to illustrate
// the use of 'as' operator
using System;
using System.Text;
using System.Collections.Generic;

class GFG {

    // Main Method
    public static void Main() {

        // taking a string variable
        string str1 = "GFG";

        // taking an Object type variable
        // assigning var1 to it
        object obj1 = str1;

        // now try it to cast to a string
        string str2 = obj1 as string;

        // checking Successfully cast or not
        if(str2 != null)
        {
            Console.WriteLine("Successfully Cast");
        }

        // now try to cast it to List
        List<string> mylist = obj1 as List<string>;

        // checking Successfully cast or not
        if(mylist != null)
        {
            Console.WriteLine("Successfully Cast");
        }
        else
        {
            Console.WriteLine("Not Successful");
        }
    }
}
```

### Output

```cs
Successfully Cast
Not Successful
```

## 示例 2

在代码中，我们取一个可以存储五个元素的 `object` 数组。第一个和第二个元素是类 `Geeks1` 和类 `Geeks2` 的实例。第三个元素是字符串，第四个元素是 `double` 值，第五个元素是 `null`。这里，`string str = obj[j] as string;` 我们使用 `as` 运算符将对象数组转换为字符串，并将结果存储到字符串中。之后，检查结果值。如果为 `null`，则打印“元素不是字符串”，如果不为空，则打印字符串。

```cs
// C# program to illustrate the
// concept of 'as' operator
using System;

// Classes
class Geeks1 { }
class Geeks2 { }

class GFG {

    // Main method
    static void Main()
    {
        // creating and initializing object array
        object[] obj = new object[5];
        obj[0] = new Geeks1();
        obj[1] = new Geeks2();
        obj[2] = "C#";
        obj[3] = 334.5;
        obj[4] = null;

        for (int j = 0; j < obj.Length; ++j) {

            // using as operator
            string str = obj[j] as string;

            Console.Write("{0}:", j);

            // checking for the result
            if (str != null) {
                Console.WriteLine("'" + str + "'");
            }
            else {
                Console.WriteLine("Is is not a string");
            }
        }
    }
}
```

### Output

```cs
0:Is is not a string
1:Is is not a string
2:'C#'
3:Is is not a string
4:Is is not a string
```