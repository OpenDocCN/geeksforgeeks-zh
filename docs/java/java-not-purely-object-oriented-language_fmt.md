# 为什么 Java 不是纯粹的面向对象语言？

> 原文：[https://www.geeksforgeeks.org/java-not-purely-object-oriented-language/](https://www.geeksforgeeks.org/java-not-purely-object-oriented-language/)

## 纯面向对象语言的定义

纯面向对象语言或完全面向对象语言是完全面向对象的语言，它支持或具有将程序内部的一切都视为对象的特性。它不支持基本数据类型（如 `int`、`char`、`float`、`bool` 等）。一种编程语言要成为纯面向对象的，需要满足七个条件。它们是：

1.  封装/数据隐藏
2.  继承
3.  多态性
4.  抽象
5.  所有预定义的类型都是对象
6.  所有用户定义的类型都是对象
7.  对对象执行的所有操作必须只能通过在对象上公开的方法来执行。

例子：Smalltalk

## 为什么 Java 不是纯面向对象语言？

Java 支持属性 1、2、3、4 和 6，但不支持上面给出的属性 5 和 7。Java 语言不是纯面向对象语言，因为它包含以下属性：

*   **原始数据类型（如 `int`、`long`、`bool`、`float`、`char` 等）作为对象：** Smalltalk 是一种“纯”面向对象的编程语言，与 Java 和 C++ 不同，因为作为对象的值和作为基元类型的值之间没有区别。在 Smalltalk 中，诸如整数、布尔值和字符等基元值也是对象。
    在 Java 中，我们有预定义的非对象类型（原语类型）。

    ```java
    int a = 5; 
    System.out.print(a);
    ```

*   **`static` 关键字：** 当我们声明一个类是静态的，那么它就可以在 Java 中不使用对象的情况下使用。如果我们使用的是静态函数或静态变量，那么我们就不能用点（`.`）来调用那个函数或变量，或者不符合面向对象特征的类对象。
*   **包装类（Wrapper Class）：** 包装类提供了将基本类型转换为对象以及将对象转换为基本类型的机制。在 Java 中，你可以使用 `Integer`、`Float` 等代替 `int`、`float` 等。我们可以不调用对象的方法就与对象进行通信。例如：使用算术运算符。

    ```java
    String s1 = "ABC" + "A" ;
    ```

即使使用包装类也不能使 Java 成为一种纯面向对象的语言，因为在内部它会使用像拆箱（Unboxing）和自动装箱（Autoboxing）这样的操作。因此，如果你创建 `Integer` 而不是 `int`，并对它进行任何数学运算，在底层，Java 将只使用原语类型 `int`。

```java
public class BoxingExample 
{
    public static void main(String[] args) 
    {
            Integer i = new Integer(10);
            Integer j = new Integer(20);
            Integer k = new Integer(i.intValue() + j.intValue());
            System.out.println("Output: "+ k);
    }
}
```

**在上面的代码中，有 2 个问题是 Java 无法像纯 OOP 一样工作：**

1.  创建 `Integer` 类时，您使用的是基本类型 `int`，即数字 10、20。
2.  做加法时，Java 使用的是原语类型 `int`。

**相关文章：** [为什么 C++ 是部分面向对象语言？](https://www.geeksforgeeks.org/c-partially-object-oriented-language/)

本文由 **Sangeet Anand** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。