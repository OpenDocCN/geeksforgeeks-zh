# Scala 中的运算符优先级

> 原文:[https://www . geeksforgeeks . org/operators-preference-in-Scala/](https://www.geeksforgeeks.org/operators-precedence-in-scala/)

[运算符](https://www.geeksforgeeks.org/operators-in-scala/)是一个符号，表示要用一个或多个操作数执行的操作。运算符是任何编程语言的基础。在具有多个不同优先级的运算符的表达式中，首先执行哪个运算符由**运算符优先级**决定。

例如，10 + 20 * 30 计算为 10 + (20 * 30)，而不是(10 + 20) * 30。
当表达式中出现两个具有相同优先级的运算符时，使用结合律。关联性可以是从右向左或从左向右。例如，“*”和“/”具有相同的优先级，并且它们的关联性是从左到右，因此表达式“100 / 10 * 10”的工作方式为“(100 / 10) * 10”。

在下表中，优先级最高的运算符出现在表的顶部，优先级最低的运算符出现在底部。

=>

| 

**操作员**

 | **类别** | 

**关联性**

 |
| ()[] | 后缀 | 从左到右 |
| ！~ | 一元 | 从右向左 |
| * / % | 乘法 | 从左到右 |
| +– | 添加剂 | 从左到右 |
| >>>>><< | 换挡 | 从左到右 |
| < < = > > = | 关系 | 从左到右 |
| ==！= | 关系等于/不等于 | 从左到右 |
| ==！= | 平等 | 从左到右 |
| & | 按位“与” | 从左到右 |
| ^ | 位异或 | 从左到右 |
| &#124; | 位包含或 | 从左到右 |
| & & | 逻辑与 | 从左到右 |
| &#124; &#124; | 逻辑或 | 从左到右 |
| =+=-= * =/= % =>>=<<=&="^= " &#124; = "</span "> | 分配 | 从右向左 |
| 、 | 逗号(独立表达式) | 从左到右 |

下面是运算符优先级的示例。

**示例:**

```scala
// Scala program to show Operators Precedence

// Creating object
object gfg
{
    // Main method
    def main(args: Array[String])
    {

        var a:Int = 20;
        var b:Int = 10;
        var c:Int = 15;
        var d:Int = 5;
        var e = 0

        // operators with the highest precedence
        // will operate first
        e = a + b * c / d; 

        /* step 1: 20 + (10 * 15) /5
            step 2: 20 + (150 /5)
        step 3:(20 + 30)*/

        println("Value of a + b * c / d is : " + e )

    }
}
```

**输出:**

```scala
Value of a + b * c / d is : 50
```

在上例中 e = a+b * c/d；这里，e 被赋值为 50，而不是 120，因为运算符*的优先级高于/ than +，所以它首先与 10 * 15 相乘，然后除以 5，然后相加为 20。