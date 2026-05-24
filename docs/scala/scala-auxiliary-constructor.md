# Scala |辅助构造器

> 原文:[https://www.geeksforgeeks.org/scala-auxiliary-constructor/](https://www.geeksforgeeks.org/scala-auxiliary-constructor/)

[构造函数](https://www.geeksforgeeks.org/scala-constructors/)用于初始化对象的状态。与方法一样，构造函数也包含一组语句(即指令)。语句在对象创建时执行。在 Scala 程序中，[主构造函数](https://www.geeksforgeeks.org/scala-primary-constructor/)以外的构造函数称为 ***辅助构造函数*** 。我们可以在 scala 类中创建任意数量的辅助构造函数，但是 Scala 类只包含一个主构造函数。
**辅助构造函数**定义为类中的方法，关键字 ***本*** 。我们可以描述多个辅助构造函数，但是它们必须有不同的参数列表。
**语法:**

```scala
def this(......)
```

让我们借助一些例子来理解辅助构造函数。
**示例#1:** 使用一个辅助构造器

## 斯卡拉

```scala
// Scala program to illustrate the
// concept of Auxiliary Constructor

// Primary constructor
class GFG( Lname: String, Tname: String)
{
    var no: Int = 0;;
    def show()
    {
        println("Language name: " + Lname);
        println("Topic name: " + Tname);
        println("Total number of articles: " + no);

    }

    // Auxiliary Constructor
    def this(Lname: String, Tname: String, no:Int)
    {

        // Invoking primary constructor
        this(Lname, Tname)
        this.no = no
    }
}

// Creating object
object Main
{
    // Main method
    def main(args: Array[String])
    {

        // Creating object of GFG class
        var obj = new GFG("Scala", "Constructor", 4);
        obj.show();
    }
}
```

**输出:**

```scala
Language name: Scala
Topic name: Constructor
Total number of articles: 4
```

在上面的例子中，我们可以看到仅使用了一个辅助构造函数，并且在该辅助构造函数中调用了主构造函数。创建 GFG 类(obj)对象后，将调用 show()函数并打印结果。

**例 2:** 使用多个辅助构造函数。

## 斯卡拉

```scala
// Scala program to illustrate the
// concept of more than concept
// Auxiliary Constructor

// Primary constructor
class Company
{
    private var Cname = ""
    private var Employee = 0

    // Creating function
    def show()
    {
        println("Language name: " + Cname);
        println("Total number of employee: " + Employee);
    }

    // An auxiliary constructor
    def this(Cname: String)
    {
        // Calls primary constructor
        this()
        this.Cname = Cname
    }

    // Another auxiliary constructor
    def this(Cname: String, Employee: Int)
    {
          // Calls previous auxiliary constructor
        this(Cname)
        this.Employee = Employee
    }
}

// Creating object
object Main
{
    // Main method
    def main(args: Array[String])
    {
        // Primary constructor
        val c1 = new Company
        c1.show()

        // First auxiliary constructor
        val c2 = new Company("GeeksForGeeks")
        c2.show()

        // Second auxiliary constructor
        val c3 = new Company("GeeksForGeeks", 42)
        c3.show()

    }
}
```

**输出:**

```scala
Language name: 
Total number of employee: 0
Language name: GeeksForGeeks
Total number of employee: 0
Language name: GeeksForGeeks
Total number of employee: 42
```

在上面的例子中，我们可以看到两个辅助构造函数是用不同的参数创建的。辅助构造函数调用了主构造函数，另一个辅助构造函数调用了先前定义的辅助构造函数。

Some Important Points About Auxiliary Constructor

*   在单个类中，我们可以创建一个或多个辅助构造函数，但是它们有不同的签名或参数列表。
*   每个辅助构造函数必须调用一个先前定义的构造函数，这将是主构造函数或先前的辅助构造函数。
*   调用构造函数可以是一个主构造函数或前一个辅助构造函数，它以文本形式出现在调用构造函数之前。
*   辅助构造函数的第一条语句必须包含**这个**关键字。