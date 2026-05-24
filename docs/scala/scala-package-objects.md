# Scala |包对象

> 原文:[https://www.geeksforgeeks.org/scala-package-objects/](https://www.geeksforgeeks.org/scala-package-objects/)

包的主要目标是保持文件模块化和易于维护。因此，我们根据创建的名称空间将项目文件保存在几个不同的文件夹或目录中，但有时我们希望一些变量、定义、类或对象能够被整个包访问。但是不可能将定义、数据变量和类型别名直接保存在包中。为此，我们有 package 对象，这样公共数据就可以在包的顶层。scala 版本引入了包对象。
**语法:**

```scala
package projectx
package src
package main
object `package`
{
  // using backticks
  val x
  // members
}

```

或者说标准的做法是。

```scala
package src
package object main
{
  val x
  // members
}

```

在上面的语法中，包对象的所有成员对 projectx.src.main 包中的所有类都是可用的，这个文件将作为 package.scala 保存在目录/包“main”中，它也对应于包名。
**示例:**
让我们有一个包对象 GFG，路径如下:-

```scala
File Path: ../src/language/GFG/package.scala
```

```scala
package language
package object GFG 
{
  val fees = "fees"
  val tax = "tax"
}

```

另一个文件 GFG.scala 里面有主方法。

```scala
File Path: ../src/language/GFG/GFG.scala
```

```scala
package language.GFG

object GFG
{
  val scala = "scala"
  val java = "java"
  val csharp = "csharp"
}

object demo
{
  def main( args : Array[String])
  {
    println(GFG.scala)
    println(GFG.csharp)
    var totalfees= tax + fees
    println(totalfees)
  }
}
```

**说明:**
正如我们所看到的，我们有直接可用的税费，因为 GFG.scala 和 package.scala 处于同一水平。

```scala
+src
   +language
        +GFG.scala
        +package.scala

```

```scala
// Scala program of package object

// package eatables.food

// Object created
object GFG
{
    val scala = "scala"
    val java = "java"
    val csharp = "csharp"
}

// Object created
object demo
{
    // Driver code
    def main( args : Array[String])
    {
        println(GFG.scala)
        println(GFG.csharp)
        var totalfees = tax + fees
        println(totalfees)
    }
}

// package object created
object `package`
{
    val fees= "fees"
    val tax= "tax"
}
```

**输出:**

```scala
scala
csharp
taxfees

```

**Package objects Important points**

*   它们可以扩展其他类和/或混合特征。

    ```scala
    package object main extends demovars
    {
      val x = a // from demovars
      val y = b // from demovars
      // members
    }

    ```

*   它们是存储隐含的好地方，而不是在[伴随对象](https://www.geeksforgeeks.org/scala-singleton-and-companion-objects/)中定义它们。
*   使用包对象，我们可以通过避免使用导入来缩短代码。

    ```scala
    package object main
    {
      val x = demovars.a // from demovars
      val y = demovars.b // from demovars
      // members
    }

    ```

*   每个包只能有一个具有相应目录目录/包名的包对象。

    ```scala
    +src
       +eatables
            +food.scala
            +package.scala // package object for eatables folder
      +drinkables
            +drinks.scala
            +package.scala // package object for drinkable folder

    ```