# 是什么让 Scala 具有可扩展性？

> 原文:[https://www.geeksforgeeks.org/what-makes-scala-scalable/](https://www.geeksforgeeks.org/what-makes-scala-scalable/)

语言的可伸缩性受到一些因素的影响，从语法细节到组件抽象结构。scala 的主要特点是它是面向对象和函数式编程的结合。它对高阶函数、尾调用优化、不可变值、模式匹配、多态性、抽象、继承等编程构造都有很好的支持。Scala 还包括自己的解释器，可以用来直接执行指令，而不需要之前的编译。另一个关键特性是*并行集合*库，旨在帮助开发人员解决并行编程模式。
其他一些特点如下:

*   Scala 很简洁。它为后端操作提供了更好的支持。与 Java 相比，Scala 程序往往短达 10 倍。它避免了反复出现的代码，以获得一些加重 Java 程序负担的结果。
    **示例:**在 Java 中，一个带有构造函数的类看起来像:

## Java 语言(一种计算机语言，尤用于创建网站)

```scala
class Geek
{
    // data members of the class.
    String name;
    int id;

    // constructor would initialized data members
    // with the values of passed arguments while
    // object of that class created.
    Geek(String name, int id)
    {
        this.name = name;
        this.id = id;
    }
}
```

*   在 Scala 中，它将被写成:

## 斯卡拉

```scala
class Geek(name: String, id: Int) {}
```

*   Scala 通过让我们提高我们设计的接口的抽象级别来帮助您管理复杂性。Java 将刺视为低级实体，在循环中逐字符遍历。Scala 代码将相同的字符串视为可以查询的更高级别的字符序列。Scala 提供了开发框架和库的工具。
    **例:**在 Java 中，要找到第一个大写字母。

## Java 语言(一种计算机语言，尤用于创建网站)

```scala
// Function to find string which has
   // first character of each word.
   static char first(String str)
   {
       for (int i = 0; i < str.length(); i++)
           if (Character.isUpperCase(str.charAt(i)))
               return str.charAt(i);
       return 0;
   }
```

*   在 scala 中，它将被写成:

## 斯卡拉

```scala
val first = str.exists(_.isUpperCase)
```

*   在 Java 代码中，字符串是低级实体，而在 Scala 中，相同的字符串被视为高级实体。在 Scala **_。isUpperCase** 是一个函数文字。

*   它支持静态类型，其中计算被形成为在编译时改变程序状态的语句。这是一种可以提高运行时效率的方法。静态类型系统根据它们持有和计算的值对变量和表达式进行分类。很像 Java 的嵌套类类型系统，它允许我们用泛型参数化类型，用抽象类型隐藏细节，用交集组合类型。
*   它是在 Java 虚拟机(JVM)上实现的，因此它可以访问所有的 Java 方法和字段，从 Java 类继承并实现 Java 接口。它不需要任何特殊的语法、显式的接口描述或粘合代码。它使用 Java 的类型，并将它们修饰得更好看。Scala 编译器将程序编译成。类文件，包含可以由 JVM 执行的字节码。Java SDK 的所有类都可以被 Scala 使用。在 Scala 的帮助下，用户可以定制 Java 类。