# 关于 Scala 的有趣事实

> 原文:[https://www.geeksforgeeks.org/interesting-fact-about-scala/](https://www.geeksforgeeks.org/interesting-fact-about-scala/)

**Scala** (发音为“skah-lah”)是马丁·奥德斯基设计的通用编程语言。斯卡拉的设计始于 2001 年瑞士洛桑的 EPFL。Scala 于 2004 年在 Java 平台上公开发布。Scala 旨在简洁并解决对 Java 的批评。Scala 源代码被编译成 Java 字节码，生成的可执行代码在 Java 虚拟机上运行。Scala 的最新版本是 2.12.8。

<center>**斯卡拉的一些有趣事实**</center>

*   **名称** : Scala 是可伸缩语言的简称。
*   **一种混合语言** : Scala 是面向对象编程(OOP)和函数式编程的融合。 *OOP* 是基于“对象”概念的编程范式，对象是以字段形式包含数据，以过程或方法形式包含代码的数据结构。另一方面，*函数式编程*是一种编程范式，计算机程序，都是由结构和元素构建的。数学函数的求值被视为计算，避免了可变数据，也避免了状态变化。这两种范例使 Scala 区别于其他编程语言。
*   **自动推断** : Scala 自动推断类型信息。类型信息仅在必要时由用户提供。
*   **可变的和不可变的变量** : Scala 允许我们在声明时使任何变量可变或不可变。关键字 ***var*** 将任何变量定义为可变的，而关键字 ***val*** 将变量定义为不可变的。
*   **无分号**:在大多数现代编程语言(C、C++、Java 等)中，分号充当*分隔符*，是每个语句后必须书写的字符。但是，Scala 不需要在每条语句后面都有分号。Scala 语句可以用换行符分隔。
*   **导入语句**:不需要在程序的开头写全部的导入语句。在 Scala 中导入类可以在任何时候完成。
*   **Scala 的特性**:除了 Java 的所有 OOP 特性之外，Scala 还有 Scheme、Standard ML、Haskell 等函数式编程语言的特性，包括 currying、类型推断、不变性、惰性求值、模式匹配。
*   **函数和过程**:在 Scala 中，函数和过程是两个不同的实体，不能互换使用。函数可以返回任何类型，并且在其原型中包含 **=** 符号。另一方面，过程没有=符号，在所有情况下都有 Unit()返回类型。函数定义中一般不鼓励打印语句。
    **例:**

    ```scala
    def func1():Int = {
    //this is a function
    //returns Int
    }

    def proc1() {
    //this is a procedure
    //returns void(Unit())
    }
    ```

*   **Higher-Order Functions**: In Scala, we can pass a function as an argument to another function. Such functions are called higher-order functions.
    **Example:**

    ```scala
    val l = List(1, 2, 3)
    l.foreach(println) // println passed as an argument to foreach function
    ```

    同样，一个函数的*返回值*可以是另一个函数。
    T3】例:

    ```scala
    def square(x:Float) = { pow(x, 2) }
    ```

*   **支持嵌套函数**:我们可以在另一个函数中定义一个函数，并根据需要使用它。嵌套函数可以从外部函数范围内的任何点调用。
*   **大数据产业** : Apache Spark 是一个开源的集群计算框架，是大数据处理广泛使用的技术。Spark 程序是用 Scala 编写的，因为它在 JVM 上具有可扩展性。Scala 是大数据开发人员在处理 Spark 项目时最常用的语言。Spark 与 Scala 的用例——阿里巴巴、网飞、Pinterest 等。