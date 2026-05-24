# Scala 中的命令行参数

> 原文: [https://www.geeksforgeeks.org/command-line-argument-in-scala/](https://www.geeksforgeeks.org/command-line-argument-in-scala/)

用户或程序员传递给 `main()` 方法的参数称为命令行参数。`main()` 方法是程序执行的入口点。`main()` 方法接受字符串数组 `args` 作为运行时参数。但是它从不接受程序中任何其他方法的参数。

**语法:**

```scala
def main(args: Array[String])
```

使用 `args` 数组访问 Scala 命令行参数，当我们扩展 `Application` 时，该数组是隐式可用的。这里有一个例子。

**示例 1:** 打印所有给定对象

## 示例 1

```scala
// Scala Program on command line argument
object CMDExample
{
    // Main method
    def main(args: Array[String])
    {
        println("Scala Command Line Argument Example");

        // You pass any thing at runtime
        // that will be print on the console
        for(arg<-args)
        {
            println(arg);
        }
    }
}
```

**要在终端上编译和执行上述程序，请遵循以下命令:**
首先保存程序 `CMDExample.scala`，然后打开 CMD/Terminal，进入保存 scala 程序的目录。

> 编译: `scalac CMDExample.scala`
> 执行: `scala CMDExample Welcome To GeeksforGeeks!`

**输出:**

```scala
Scala Command Line Argument Example
Welcome
To
GeeksforGeeks!
```

![](img/f8014975232a49d87e65a6efb6db973a.png)

**例 2:** 打印一些运行时给出的对象

## 示例 2

```scala
// Scala Program on command line argument
object CMDExample
{
    // Main method
    def main(args: Array[String])
    {
        println("Scala Command Line Argument Example");

        // You pass any thing at runtime
        // that will be print on the console
        println(args(0));
        println(args(2));
    }
}
```

**要在终端上编译和执行上述程序，请遵循以下命令:**

> 编译: `scalac CMDExample.scala`
> 执行: `scala CMDExample 1 Welcome To GeeksforGeeks! 2`

**输出:**

```scala
Scala Command Line Argument Example
Welcome
To
```

![](img/b21d5076e9fe2632bc5977d731f6391e.png)

**注意:** 如果给定的索引在数组中不存在，那么你会发现这个错误

![](img/ce96691af0d2debf8d3d366515acdde7.png)