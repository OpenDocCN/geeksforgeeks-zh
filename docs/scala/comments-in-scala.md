# 斯卡拉评论

> 原文:[https://www.geeksforgeeks.org/comments-in-scala/](https://www.geeksforgeeks.org/comments-in-scala/)

在我们的代码中，注释是解释器/编译器忽略的实体。我们通常用它们来解释代码，也隐藏代码细节。这意味着注释不会成为代码的一部分。它将不会被执行，而是仅用于详细解释代码。

换句话说， **scala 注释**是不被编译器或解释器执行的语句。注释可用于提供关于变量、类、方法或任何语句的解释或信息。这也可以用来隐藏程序代码细节。

在 Scala 中，有三种类型的注释:

1.  单行注释。
2.  多行注释。
3.  文件注释。

在这里，我们将解释每一种类型及其语法和示例:

<center>**Scala 单行注释**</center>

当我们在 Scala 中只需要一行注释时，也就是说，我们只想写一行注释，那么我们可以使用注释前面的字符“//”。这些字符将使该行成为注释。
**语法:**

```scala
//Comments here( Text in this line only is considered as comment )

```

**示例:**

```scala
// This is a single line comment.

object MainObject 
{ 
    def main(args: Array[String]) 
    { 
        println("Single line comment above") 
    } 
} 
```

**输出:**

```scala
Single line comment above
```

<center>**Scala 多行注释**</center>

如果我们的注释跨越多行，我们可以使用多行注释。我们在注释周围使用字符'/* '和' */'。也就是说，我们在这些字符之间写一个文本，它就变成了一个注释。
**语法**

```scala
/*Comment starts
continues
continues
.
.
.
Commnent ends*/

```

**例**

```scala
// Scala program to show multi line comments 

object MainObject 
{ 
    def main(args: Array[String]) 
    { 
        println("Multi line comments below")     
    } 

    /*Comment line 1 
     Comment line 2 
     Comment line 3*/
} 
```

**输出**

```scala
Multi line comments below
```

<center>**Scala 中的文档注释**</center>

文档注释用于快速查找文档。编译器使用这些注释来记录源代码。我们有以下语法来创建文档注释:
**语法**

```scala
/**Comment start
*
*tags are used in order to specify a parameter
*or method or heading
*HTML tags can also be used 
*such as <h1>
*
*comment ends*/

```

**例**

```scala
// Scala program to show Documentation comments

object MainOb 
{ 
    def main(args: Array[String])   
    { 
        println("Documentation comments below")     
    } 

    /** 
    * This is geek for geeks 
    * geeks coders
    * 
    */
}
```

**输出**

```scala
Documentation comments below
```

对于这样一个注释的声明，请键入字符'/** '，然后键入一些内容，或者我们可以按。所以每次我们按回车键的时候，IDE 都会放一个' * '进去。若要结束注释，请在其中一个星号(*)后键入“/”。