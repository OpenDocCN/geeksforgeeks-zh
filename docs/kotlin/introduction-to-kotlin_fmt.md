# 柯特林介绍

> 原文: [https://www.geeksforgeeks.org/introduction-to-kotlin/](https://www.geeksforgeeks.org/introduction-to-kotlin/)

`Kotlin` 是 `JetBrains` 开发的一种静态类型的通用编程语言，已经构建了像 `IntelliJ IDEA`、`PhpStorm`、`Appcode` 等世界级的 `IDE`。它于 2011 年由 `JetBrains` 首次引入，是 `JVM` 的一种新语言。`Kotlin` 是面向对象的语言，是一种比 `Java` “更好的语言”，但仍然可以与 `Java` 代码完全互操作。

`Kotlin` 由谷歌赞助，2017 年宣布为**安卓开发**的官方语言之一。

## 柯特林示例

```kt
fun main()
{
    println("Hello Geeks");
}
```

## 柯特林的主要特征

1.  **静态类型化** – 静态类型化是一种编程语言特性，意味着每个变量和表达式的类型在编译时都是已知的。虽然它是静态类型语言，但它不需要您显式指定您声明的每个变量的类型。
2.  **Data Classes** – 在 `Kotlin` 中，有 `Data Classes`，这可以自动生成诸如 `equals`、`hashCode`、`toString`、`getters/setters` 等样板代码。

考虑以下示例：

```kt
/*     Java Code     */
class Book {
    private String title;
    private Author author;
    public String getTitle()
    {
        return title;
    }
    public void setTitle(String title)
    {
        this.title = title;
    }
    public Author getAuthor()
    {
        return author;
    }
    public void setAuthor(Author author)
    {
        this.author = author;
    }
}
```

但是在 `Kotlin`，只有一行用来定义上面的类：

```kt
/* Kotlin Code */
data class Book(var title:String, var author:Author)
```

3.  **简洁** – 它大大减少了用其他面向对象编程语言编写的额外代码。
4.  **Safe** – 它通过将可空性作为其系统的一部分来支持，从而避免了最烦人和恼人的 `NullPointerExceptions`。
    `Kotlin` 中的每个变量默认都是非空的。

```kt
String s = "Hello Geeks"    // Non-null
```

如果我们试图赋予 `s` 空值，那么它会产生编译时错误。所以，

```kt
s = null                    // compile time error
```

要将空值赋给任何字符串，应该将其声明为可空。

```kt
String nullableStr? = null  // compiles successfully
```

`length()` 函数也对可空字符串禁用。

5.  **与 Java 互操作** – `Kotlin` 运行在 `Java` 虚拟机 (`JVM`) 上，因此完全可以与 `Java` 互操作。我们可以很容易地访问使用来自 `Kotlin` 的 `Java` 代码和来自 `Java` 的 `Kotlin` 代码。
6.  **Functional and Object Oriented Capabilities** – `Kotlin` 有丰富的许多有用的方法，包括高阶函数、`lambda` 表达式、运算符重载、惰性求值、运算符重载等。
    高阶函数是一个接受函数作为参数或返回一个函数或两者兼有的函数。

## 高阶函数示例

```kt
fun myFun(company: String,product: String, fn: (String,String) -> String): Unit {
    val result = fn(company,product)
    println(result)
}

fun main(args: Array<String>){
    val fn:(String,String)->String={org,portal->"$org develops $portal"}
    myFun("JetBrains","Kotlin",fn)
}
```

**输出:**

```kt
JetBrains develops Kotlin
```

7.  **智能强制转换** – 它显式地强制转换不可变的值，并将该值自动插入其安全强制转换中。
    如果我们试图访问一个可空类型的字符串 (`String? = "BYE "`) 而没有安全转换，它将生成编译错误。

```kt
fun main(args: Array<String>){
    var string: String? = "BYE"          
    print(string.length)       // compile time error
}
```

```kt
fun main(args: Array<String>){
    var string: String? = "BYE"
    if(string != null) {               // smart cast
        print(string.length) 
    }
}
```

8.  **编译时间** – 性能更高，编译时间快。
9.  **工具友好型** – 具有出色的工具支持。任何 `Java IDEs` —— `IntelliJ IDEA`、`Eclipse` 和 `Android Studio` 都可以用于 `Kotlin`。我们也可以从命令行运行 `Kotlin` 程序。

## 科特林语言优势

*   易于学习 – `Basic` 几乎类似于 `Java`。如果有人用 `Java` 工作，那么很容易理解。
*   `Kotlin` 是多平台的 —— 所有 `Java IDEs` 都支持 `Kotlin`，因此您可以编写程序并在任何支持 `JVM` 的机器上执行它们。
*   比 `Java` 安全多了。
*   它允许通过使用高级框架在新的 `Kotlin` 项目中使用 `Java` 框架和库，而不需要在 `Java` 中更改整个项目。
*   `Kotlin` 编程语言，包括编译器、库和所有工具，是完全免费和开源的，可在 `github` 上获得。这里是 `Github` [https://github.com/JetBrains/kotlin](https://github.com/JetBrains/kotlin) 的链接。

## 柯特林语言的应用

*   你可以用 `Kotlin` 来构建安卓应用。
*   `Kotlin` 还可以编译成 `JavaScript`，并使其可用于前端。
*   它也是为 `Web` 开发和服务器端开发而设计的。