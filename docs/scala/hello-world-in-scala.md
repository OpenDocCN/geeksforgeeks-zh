# 斯卡拉的 Hello World

> 原文:[https://www.geeksforgeeks.org/hello-world-in-scala/](https://www.geeksforgeeks.org/hello-world-in-scala/)

你好世界！当你钻研一门新的编程语言时，这个程序是最基本的，也是第一个程序。这只是打印你好世界！在输出屏幕上。在 [Scala](https://www.geeksforgeeks.org/introduction-to-scala/) 中，一个基本程序由以下内容组成:

***   target*   Main method*   Statement or expression**

**示例:**

```scala
// Scala program to print Hello World! 
object Geeks 
{
    // Main Method 
    def main(args: Array[String]) 
    {
        // prints Hello World
        println("Hello World!") 
    }
}
```

**输出:**

```scala
Hello World!
```

**说明:**

*   **对象极客:**对象是用来创建*对象*的关键字。对象是类的实例。这里“极客”是对象的名称。
*   **def Main(args:Array[String]):**def 是 Scala 中的关键字，用来定义函数，*“Main”*是 *Main Method 的名字。args: Array[String]* 用于命令行参数。
*   **println(“你好世界！”):** println 是 Scala 中的一种方法，用于*在控制台上显示*输出。

#### 如何运行 Scala 程序？

*   **要使用在线 Scala 编译器:**我们可以使用各种在线 IDE。它可以用来运行 Scala 程序而无需安装。
*   **Using Command-Line:** Make sure we have the Java 8 JDK (also known as 1.8). run javac -version in the command line and make sure we see javac 1.8.___ If we don’t have version 1.8 or higher, [Install the JDK](https://www.geeksforgeeks.org/setting-environment-java/) Firstly, open a text editor Notepad or Notepad++. write the code in the text editor and save the file with (.scala) extension. open the command prompt follow step by step process on your system.

    ```scala
    // Scala program to print Hello World! 
    object Geeks 
    {
        // Main Method 
        def main(args: Array[String]) 
        {
            // prints Hello World
            println("Hello World!") 
        }
    }
    ```

    第一步:使用 *scalac Hello 编译上述文件。Scala* 编译后会生成一个 Geeks.class 文件，类文件名和对象名相同(这里对象名是 Geeks)。
    第二步:现在打开对象名为*的命令 scala Geeks* 。它会给出结果。
    ![](img/60410ab59fb9a15a355e827902c71b42.png)

*   **使用 Scala IDE:** IDE 像 IntelliJ IDEA 一样，ENSIME 可以轻松运行 Scala 程序。在文本编辑器中编写代码，然后按运行它。