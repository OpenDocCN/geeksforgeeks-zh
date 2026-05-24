# Scala 中的无参数方法

> 原文:[https://www . geeksforgeeks . org/无参数方法 in-scala/](https://www.geeksforgeeks.org/parameterless-method-in-scala/)

先决条件–[Scala |函数](https://www.geeksforgeeks.org/scala-functions-basics/)

一个 ***无参数*** 方法是一个不取参数的函数，由不存在任何**空括号**定义。无参数函数的调用应该不带括号。这允许将 *def* 更改为 *val* ，而客户端代码没有任何更改，客户端代码是 ***统一访问原则*** 的一部分。

**示例:**

```scala
// Scala program to illustrate
// Parameterless method invocation
class GeeksforGeeks(name: String, ar: Int)
{
    // A parameterless method
    def author = println(name)
    def article = println(ar)

    // An empty-parenthesis method
    def printInformation() = 
    {
        println("User -> " + name + ", Articles -> " + ar)
    }
}

// Creating object 
object Main 
{ 
    // Main method
    def main(args: Array[String]) 
    { 

        // Creating object of Class 'Geeksforgeeks'
        val GFG = new GeeksforGeeks("John", 50)
        GFG.author     // calling method without parenthesis
    } 
} 
```

**输出:**

```scala
John
```

使用无参数方法通常有两种惯例。一个是没有任何参数的时候。第二种是当方法不改变**可变状态**时。通过定义带有括号的副作用的方法，必须避免调用看起来像字段选择的无参数方法。
调用无参数方法的例子，括号给出编译错误。

**示例:**

```scala
// Scala program to illustrate
// Parameterless method invocation
class GeeksforGeeks(name: String, ar: Int)
{
    // A parameterless method
    def author = println(name)
    def article = println(ar)

    // An empty-parenthesis method
    def printInformation() = 
    {
        println("User -> " + name + ", Articles -> " + ar)
    }
}

// Creating object
object Main 
{ 
    // Main method
    def main(args: Array[String]) 
    { 

        // Creating object of Class 'Geeksforgeeks'
        val GFG = new GeeksforGeeks("John", 50)
        GFG.author()     //calling method without parenthesis
    } 
} 
```

**输出:**

> prog.scala:23:错误:单元不接受参数
> gfg . author()//调用不带括号的方法
> ^
> 发现一个错误

**注意:**空括号方法可以在没有括号的情况下调用，但通常建议并接受使用括号调用空括号方法。