# 安卓中 Java 和 Kotlin 的区别举例

> 原文：[https://www.geeksforgeeks.org/difference-between-java-and-kotlin-in-android-with-examples/](https://www.geeksforgeeks.org/difference-between-java-and-kotlin-in-android-with-examples/)

## Kotlin

Kotlin 是一种**跨平台、静态类型、通用的编程语言**，配合**类型推断**。Kotlin 旨在与 Java 完全互操作，但是类型推断允许其语法更加简洁。Kotlin 由 JetBrains 开发，并通过 Kotlin 基金会获得谷歌赞助。

## Java 语言

Java 是一种面向对象编程语言，由詹姆斯·高斯林和他在太阳微系统公司的同事于 1991 年开发。这种语言最初被称为“Oak”。它是作为一种成熟的编程语言发展起来的，在这种语言中，人们可以完成相同种类的任务，并解决在其他编程语言（如 BASIC、C++ 等）中可以解决的类似问题。

### 在安卓系统中使用 Kotlin 替代 Java 语言

将 [Kotlin](https://www.geeksforgeeks.org/kotlin-android-tutorial/) 引入[安卓](https://www.geeksforgeeks.org/android-app-development-fundamentals-for-beginners/)开发的最大原因是为了减少代码行数，让开发更方便。利用 Java 可以完成的一切都可以利用 Kotlin 进行安卓开发。

### 例如：

*   **不需要 `findViewById`：** 用于查找给定 ID 的第一个后代视图。
    **Java**
    ```java
    TextView textView = (TextView) findViewById(R.id.textView);
    textView.setText("Hello World");
    ```
    **Kotlin**
    ```kotlin
    textView.setText("Hello World")
    ```
*   **摆脱空指针异常**
    [空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)是 Java 设计者失望的巨大根源。在 Kotlin 中，默认情况下，所有类型都是不可空的（不能保存空值）。如果代码试图在 Kotlin 中使用或返回 `null`，则会显示编译时错误。
    ```kotlin
    var a: String = "abc"
    // 编译错误
    a = null
    ```
*   **数据类：** 我们经常创建类来保存其中的一些数据。在这样的类中，一些标准函数通常可以从数据中导出。在 Kotlin 中，这种类型的类被称为[数据类](https://www.geeksforgeeks.org/kotlin-data-classes/)，并被标记为 `data`。
    ```kt
    data class User(val name: String, val age: Int)
    ```

### 这两种语言根据其特点有很多不同

| 特征 | Kotlin | Java 语言 |
| --- | --- | --- |
| 1.扩展函数 | 它已经在 Kotlin 中提供 | 在 Java 中，我们需要创建类 |
| 2.空安全 | 它在 Kotlin 中提供 | 它在 Java 中不可用 |
| 3.静态成员 | Kotlin 没有类的静态成员 | 它在 Java 语言中存在 |
| 4.字符串模板 | 是的，在 Kotlin 中有两种类型的字符串 | 它在 Java 中也是可用的，但是它不支持像 Kotlin 这样的表达式 |
| 5.通配符类型 | 它在 Kotlin 中不可用 | 在 Java 中可用 |
| 6.智能转换 | Kotlin 提供 | Java 中不可用 |
| 7.无检查异常 | Kotlin 完全删除了检查异常 | 这在 Java 中是有问题的 |
| 8.操作符重载 | Kotlin 允许用户提供操作符的函数实现 | 运算符与特定的 Java 类型相关联 |
| 9.构造函数 | 它有主构造函数和次构造函数 | 构造函数可以用来获取参数来初始化属性 |
| 10.类型系统 | 它提供可空性支持、类型推断和泛型 | 还有其他种类的引用类型与类的基本概念相关 |

尽管这两种语言之间存在差异，但是 Java 和 Kotlin 是 100% **互操作的**。可以从 Java 调用 Kotlin 代码，也可以从 Kotlin 调用 Java 代码。因此，在同一个项目中，Kotlin 和 Java 类是可以并行存在的，而且所有的东西都可以编译。