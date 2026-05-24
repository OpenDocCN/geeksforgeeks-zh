# Scala 这个关键词

> 原文:[https://www.geeksforgeeks.org/scala-this-keyword/](https://www.geeksforgeeks.org/scala-this-keyword/)

关键词是语言中用来表示某些预定义动作或某些内部过程的词。当我们想要介绍一个类的当前对象时，我们使用 ***这个*** 关键字。然后使用点运算符(。)，我们可以使用这个关键字来引用实例变量、方法和构造函数。**这个**关键字也和[辅助构造函数](https://www.geeksforgeeks.org/scala-auxiliary-constructor/)一起使用。

让我们用一些例子来理解*这个*关键词。

**示例#1:**

## 斯卡拉

```scala
// Scala program to illustrate this keyword
class Addition(i:Int)
{
    // using this keyword
    def this(i:Int, j:Int)
    {
        this(i)
        println(i + " + " + j + " = " + { i + j })
    }
}

// Creating object
object GFG
{
    // Main method
    def main(args:Array[String])
    {
        var add = new Addition(15, 12)
    }

}
```

**输出:**

```scala
15 + 12 = 27
```

在上面的例子中，定义了一个由一个参数组成的类加法，在这个类中，我们使用这个关键字创建了一个具有两个参数 **i** 和 **j** 的方法。在这个方法中，还调用了一个主构造函数(即这个(I))。

**例 2:**

## 斯卡拉

```scala
// Scala program to illustrate this keyword
class geeks
{
    var Lname: String = ""
    var Articles = 0

    // Using this keyword
    def this(Lname:String, Articles:Int )
    {
        this()
        this.Lname = Lname
        this.Articles = Articles

    }
    def show()
    {
        println("Language name " + Lname +
                " published article " + Articles )
    }
}

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String])
    {
        var GeeksForGeeks = new geeks( "Scala", 105)
        GeeksForGeeks.show()
    }
}
```

**输出:**

```scala
Language name Scala published article 105
```

正如我们所看到的，在上面的例子中，一个用这个关键字定义的辅助构造函数和一个用这个关键字调用的主构造函数。实例变量(即 Lname、Articles)也使用**点(。)**运算符。