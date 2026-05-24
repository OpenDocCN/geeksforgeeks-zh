# Scala 介绍

> 原文:[https://www.geeksforgeeks.org/introduction-to-scala/](https://www.geeksforgeeks.org/introduction-to-scala/)

[Scala](https://www.geeksforgeeks.org/scala-programming-language/) 是一种通用、高级、多范式的编程语言。它是一种纯面向对象的编程语言，也为函数式编程方法提供了支持。在 Scala 中，没有原始数据的概念，因为一切都是对象。它旨在以精炼、简洁和类型安全的方式表达一般的编程模式。Scala 程序可以转换成字节码，可以在 [**JVM**](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) **(Java 虚拟机)**上运行。Scala 代表*可扩展*语言。它还提供了 [**Javascript**](https://www.geeksforgeeks.org/how-to-be-a-javascript-developer-without-knowing-javascript/) 运行时。Scala 受 Java 和其他一些编程语言如 Lisp、Haskell、Pizza 等的影响很大。

**Scala 的进化:**
Scala 是由瑞士洛桑联邦理工学院(EPFL) 的编程方法教授*马丁·奥德斯基*和一位德国计算机科学家设计的。马丁·奥德斯基也是*Java 编译器*、*通用 Java* 和 *EPFL 漏斗*编程语言的共同创造者。他在 2001 年开始设计 Scala。Scala 最早于 *2004* 在 Java 平台上公开发布，作为其第一个版本。在*2004 年 6 月*中，Scala 被修改为 [**。Net Framework**](https://www.geeksforgeeks.org/c-net-framework-basic-architecture-component-stack/) 。很快在 2006 年又有了第二个版本，即 *(v2.0* )。在 2012 年的 *JavaOne* 大会上，Scala 获得了“脚本碗”大赛的冠军。从 2012 年 6 月开始，Scala 不再为 [**提供任何支持。Net Framework**](https://www.geeksforgeeks.org/c-net-framework-basic-architecture-component-stack/) 。scala 的*最新版本是 2018 年 4 月 27 日发布的 2.12.6* 。

#### 为什么是 Scala？

Scala 在程序员中受欢迎有很多原因。原因很少:

*   **易于启动:** Scala 是一种高级语言，因此它更接近于其他流行的编程语言，如 Java、C、C++。因此，对任何人来说，学习 Scala 都变得非常容易。对于 Java 程序员来说，Scala 更容易学习。
*   **包含最佳特性:** Scala 包含了 C、C++、Java 等不同语言的特性。这使得 it 更加有用、可扩展和高效。
*   **与 Java 的紧密集成:**Scala 的源代码是这样设计的，它的编译器可以解释 Java 类。此外，它的编译器可以利用框架、Java 库和工具等。编译后，Scala 程序可以在 JVM 上运行。
*   **基于网络的&桌面应用程序开发:**对于网络应用程序，它通过编译成 JavaScript 来提供支持。类似地，对于桌面应用程序，它可以被编译成 JVM 字节码。
*   **大公司使用:**像苹果、推特、沃尔玛、谷歌等大部分热门公司。将他们的大部分代码从其他语言转移到 Scala。原因是它具有高度可伸缩性，可以用于后端操作。

**注:**人们总认为 Scala 是 [**Java**](https://www.geeksforgeeks.org/java/) 的延伸。但这不是真的。它只是与 Java 完全互操作。Scala 程序被转换成 [**。类文件**](https://www.geeksforgeeks.org/java-class-file/) 其中包含 Java 字节码编译成功后然后可以在 JVM(Java 虚拟机)上运行。

#### 从 Scala 编程开始

**找编译器:**网上有各种各样的 IDE，比如[**geeks forgeeks IDE**](https://ide.geeksforgeeks.org/)[**Scala 提琴 IDE**](https://scalafiddle.io/) 等。它可以用来运行 Scala 程序而无需安装。

**在 Scala 中编程:**由于 Scala 在语法上与其他广泛使用的语言有很多相似之处，所以在 Scala 中编码和学习更容易。程序可以在任何广泛使用的文本编辑器中用 Scala 编写，如**记事本++** 、 **gedit** 等。或者任何文本编辑器。写完程序后，保存扩展名为**的文件。sc** 或**。scala** 。

**对于 Windows & Linux:** 在 Windows 或 Linux 上安装 Scala 之前，您必须在系统上安装 **Java 开发工具包(JDK) 1.8** 或更高版本。因为 Scala 总是在 **Java 1.8** 或更高版本上运行。
在本文中，我们将讨论如何在在线 IDE 上运行 Scala 程序。

**示例:**一个简单的程序打印*你好极客们！*采用面向对象的方法。

## 斯卡拉

```scala
// Scala program to print Hello, Geeks!
// by using object-oriented approach

// creating object
object Geeks {

// Main method
def main(args: Array[String])
{

    // prints Hello, Geeks!
    println("Hello, Geeks!")
}
}
```

**输出:**

```scala
Hello, Geeks!
```

**注释:**注释用于解释代码，使用方式与 Java 或 C 或 C++类似。编译器忽略注释条目，并且不执行它们。注释可以是单行或多行。

*   **单行注释:**
    **语法:**

```scala
// Single line comment
```

*   **多行注释:**
    **语法:**

```scala
/* Multi-line comments
   syntax */
```

**对象极客:**对象是用于创建对象的关键字。这里“**极客**”是对象的名字。
**def main(args:Array[String]):***def*是 Scala 中用于定义函数的关键字，“Main”是 Main Method 的名称。**参数:数组[字符串]** 用于命令行参数。
**println(“你好，极客！”):** *println* 是 Scala 中的一个方法，用来在控制台上显示字符串。

> **注意:**也有一种函数方法可以用在 Scala 程序中。一些在线集成开发环境不支持它。我们将在以后的文章中讨论它。

#### 斯卡拉的特点

它有许多不同于其他语言的特点。

*   **面向对象:**Scala 中的每个值都是一个对象，所以它是一种**纯**面向对象的编程语言。Scala 中的类和特性描述了对象的行为和类型。
*   **Functional:** 它也是一种函数式编程语言，因为每个函数都是一个值，每个值都是一个对象。它支持高阶函数、嵌套函数、匿名函数等。
*   **静态类型化:**验证和实施类型约束的过程是在编译时在 Scala 中完成的。不同于其他静态类型的编程语言，如 C++、 [C](https://www.geeksforgeeks.org/c-language-set-1-introduction/) 等。，Scala 不期望用户提供冗余的类型信息。在大多数情况下，用户不需要指定类型。
*   **可扩展:**新的语言构造可以以库的形式添加到 Scala 中。Scala 被设计成使用 [*JRE(Java 运行时环境)*](https://www.geeksforgeeks.org/differences-jdk-jre-jvm/) 进行插值。
*   **并发&同步处理:** Scala 允许用户以不可变的方式编写代码，这使得应用并行性(同步)和并发性变得容易。
*   **在 JVM 上运行&可以执行 Java 代码:** Java 和 Scala 有一个共同的运行时环境。因此用户可以很容易地从 Java 转移到 Scala。Scala 编译器将程序编译成[***。类文件***](https://www.geeksforgeeks.org/java-class-file/) ，包含 [*JVM*](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 可以执行的字节码。Java SDK 的所有类都可以被 Scala 使用。在 Scala 的帮助下，用户可以定制 Java 类。

**优势:**

*   Scala 的复杂特性提供了更好的编码和性能效率。
*   元组、宏和函数是 Scala 的进步。
*   它结合了面向对象和函数式编程，这反过来又使它成为一种强大的语言。
*   它是高度可扩展的，因此为后端操作提供了更好的支持。
*   它降低了与 Java 中更高的线程安全性相关的风险。
*   由于功能性方法，一般来说，用户最终会有更少的代码行和错误，从而提高生产率和质量。
*   由于懒计算，Scala 只在程序需要表达式时才计算表达式。
*   Scala 中没有静态方法和变量。它使用 [singleton](https://www.geeksforgeeks.org/singleton-class-java/) 对象(源文件中有一个对象的类)。
*   它还提供了特征概念。特性是抽象和非抽象方法的集合，可以编译成 Java 接口。

**缺点:**

*   有时，两种方法会让 Scala 变得难以理解。
*   与 Java 开发人员相比，Scala 开发人员数量有限。
*   它没有真正的尾部递归优化，因为它运行在 JVM 上。
*   它总是围绕着面向对象的概念，因为在 Scala 中，每个函数都是值，每个值都是一个对象。

**应用:**

*   它主要用于数据分析与火花。
*   用于开发网络应用程序和应用编程接口。
*   它提供了开发框架和库的工具。
*   首选在后端操作中使用，以提高开发人员的工作效率。
*   并行批处理可以使用 Scala 来完成。