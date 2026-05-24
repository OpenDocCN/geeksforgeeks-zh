# Scala |主构造函数

> 原文:[https://www.geeksforgeeks.org/scala-primary-constructor/](https://www.geeksforgeeks.org/scala-primary-constructor/)

[构造函数](https://www.geeksforgeeks.org/scala-constructors/)用于初始化对象的状态。与方法一样，构造函数也包含一组语句(即指令)。语句在对象创建时执行。当我们的 Scala 程序只包含一个构造函数时，这个构造函数被称为**主构造函数**。

主构造函数和类共享同一个主体，这意味着我们不需要显式创建构造函数。

**语法:**

```scala
class class_name(Parameter_list) {
// Statements...
}
```

**Scala 中关于主构造函数的一些要点–**

*   主构造函数可以有零个或多个参数。
*   在构造函数中使用 ***var*** 来声明参数表的参数，那么该值可能会改变。Scala 还为该字段生成 getter 和 setter 方法。
*   使用构造函数中的 ***值*** 来声明参数列表的参数，那么该值不能改变，Scala 也只为该字段生成一个 getter 方法。
*   参数列表的参数在构造函数中不用**或 ***var*** 来声明，那么字段的可见性就非常紧凑，Scala 不会为该字段生成任何 getter 和 setter 方法。**
*   **参数列表的参数在构造函数中使用*私有值*或*变量*声明，然后它阻止为该字段生成任何 getter 和 setter 方法。因此，该类的成员可以访问这些字段。**
*   **在 Scala 中，只允许主构造函数调用超类构造函数。**

**让我们用一些例子来更好地理解它。**

****示例#1:** 带参数表的主构造函数**

## **斯卡拉**

```scala
// Scala program to illustrate the
// concept of primary constructor

// Creating a primary constructor
// with parameter-list
class GFG(Lname: String, Tname: String, article: Int)
{
    def show()
    {
        println("Language name: " + Lname);
        println("Topic name: " + Tname);
        println("Total published articles:" + article);
    }
}

// Creating object
object Main
{
    // Main method
    def main(args: Array[String])
    {

        // Creating and initializing
        // object of GFG class
        var obj = new GFG("Scala", "Constructors", 14);
        obj.show();
    }
}
```

****输出:****

```scala
Language name: Scala
Topic name: Constructors
Total published articles:14
```

**在上例中 **Lname、Tname** 和 **article** 是主构造函数的参数，display 是打印值的函数。

**例 2:** 带参数表的主构造函数。**

## **斯卡拉**

```scala
// Scala program to illustrate the
// concept of default primary constructor

class GFG
{
    def show()
    {
        println("Welcome to Geeksforgeeks");
    }
}

// Creating object
object Main
{
    // Main method
    def main(args: Array[String])
    {

        // Creating object of GFG class
        var obj = new GFG();
        obj.show();
    }
}
```

****输出:****

```scala
Welcome to Geeksforgeeks
```

**在上面的例子中，我们可以看到编译器会在我们创建类的对象时自动**创建一个主构造函数，这个构造函数被称为默认的主构造函数。

**示例#3:** 带默认值的主构造函数****

## ****斯卡拉****

```scala
**// Scala program to illustrate the
// concept of primary constructor

// Creating primary constructor with default values
class GFG(val Lname: String = "Scala",
        val Tname: String = "Constructors")
{
    def show()
    {
        println("Language name: " + Lname);
        println("Topic name: " + Tname);

    }
}

// Creating object
object Main
{
    // Main method
    def main(args: Array[String])
    {
        // Creating object of GFG class
        var obj = new GFG();
        obj.show();
    }
}**
```

******输出:****** 

```scala
**Language name: Scala
Topic name: Constructors**
```

******示例#4:** 通过使用 private 关键字，主构造函数是私有的。****

## ****斯卡拉****

```scala
**// Scala program to illustrate the
// concept of primary constructor
// by using private keyword
class GFG private
{
    // Define method
    override def toString = "Welcome to GeeksForGeeks."
}

// Creating object of class GFG
object GFG
{
    // Creating object   
    val gfg = new GFG
    def getObject = gfg
}

object SingletonTest extends App
{

  // this won't compile
  // val gfg = new GFG
  // this works
  val gfg = GFG.getObject
  println(gfg)
}**
```

******输出:******

```scala
**Welcome to GeeksForGeeks.**
```

****从上面的例子中我们可以看到， **private** 关键字被用在类名和构造器参数列表之间。 *val gfg = new GFG* (这行代码)甚至不会编译，因为主构造函数是私有的。****