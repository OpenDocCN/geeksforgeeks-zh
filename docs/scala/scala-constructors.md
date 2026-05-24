# Scala 构造函数

> 原文:[https://www.geeksforgeeks.org/scala-constructors/](https://www.geeksforgeeks.org/scala-constructors/)

***构造函数*** 用于初始化对象的状态。与方法一样，构造函数也包含在 ***对象创建*** 时执行的语句(即指令)的集合。
Scala 支持两种类型的构造函数:

#### 主构造函数

当我们的 Scala 程序只包含一个构造函数时，这个构造函数被称为主构造函数。主构造函数和类共享同一个主体，这意味着我们不需要显式创建构造函数。

**语法:**

```scala
class class_name(Parameter_list){
// Statements...
}
```

**重要点:**

*   在上面的语法中，主构造函数和类共享同一个**主体**，因此，除了方法声明之外，类主体中定义的任何东西都是主构造函数的一部分。
    T3】例:

## 斯卡拉

```scala
// Scala program to illustrate the
// concept of primary constructor

// Creating a primary constructor
// with parameter-list
class GFG(Aname: String, Cname: String, Particle: Int)
{
    def display()
    {
        println("Author name: " + Aname);
        println("Chapter name: " + Cname);
        println("Total published articles:" + Particle);
    }
}

object Main
{
    def main(args: Array[String])
    {

        // Creating and initializing
        // object of GFG class
        var obj = new GFG("Ankita", "Constructors", 145);
        obj.display();
    }
}
```

**输出:**

```scala
Author name: Ankita
Chapter name: Constructors
Total published articles:145
```

*   主构造函数可以包含零个或多个参数。
*   如果我们没有在我们的 Scala 程序中创建一个构造函数，那么当我们创建你的类的一个对象时，编译器会自动**创建一个主构造函数，这个构造函数被称为默认的主构造函数。它不包含任何参数。
    T3】例:**

## **斯卡拉**

```scala
// Scala program to illustrate the
// concept of default primary constructor

class GFG
{
    def display()
    {
        println("Welcome to Geeksforgeeks");
    }
}

object Main
{
    def main(args: Array[String])
    {

        // Creating object of GFG class
        var obj = new GFG();
        obj.display();
    }
}
```

****输出:****

```scala
Welcome to Geeksforgeeks
```

*   **如果构造函数参数列表中的参数是使用 var 声明的，那么字段的值可能会改变。Scala 还为该字段生成 getter 和 setter 方法。** 
*   **如果构造函数参数列表中的参数是使用 val 声明的，那么字段的值不能改变。Scala 还为该字段生成了一个 getter 方法。** 
*   **如果构造函数参数列表中的参数是在不使用 val 或 var 的情况下声明的，那么字段的可见性将受到很大限制。Scala 不会为该字段生成任何 getter 和 setter 方法。** 
*   **如果构造函数参数列表中的参数是使用私有 val 或 var 声明的，那么它将阻止为该字段生成任何 getter 和 setter 方法。因此，该类的成员可以访问这些字段。** 
*   **在 Scala 中，只允许主构造函数调用超类构造函数。**
*   **在 Scala 中，我们可以通过在类名和构造函数参数列表之间使用私有关键字来使主构造函数私有。
    **语法:****

```scala
// private constructor with two argument
class GFG private(name: String, class:Int){
// code..
}

// private constructor without argument
class GFG private{
// code...
}
```

*   **在 Scala 中，我们可以在构造函数声明中给出默认值。
    **例:****

## **斯卡拉**

```scala
// Scala program to illustrate the
// concept of primary constructor

// Creating primary constructor with default values
class GFG(val Aname: String = "Ankita",
          val Cname: String = "Constructors")
{
    def display()
    {
        println("Author name: " + Aname);
        println("Chapter name: " + Cname);

    }
}

object Main
{
    def main(args: Array[String])
    {
        // Creating object of GFG class
        var obj = new GFG();
        obj.display();
    }
}
```

****输出:****

```scala
Author name: Ankita
Chapter name: Constructors 
```

#### **辅助构造器**

**在 Scala 程序中，主构造函数以外的构造函数称为辅助构造函数。我们可以在程序中创建任意数量的辅助构造函数，但是一个程序只包含一个主构造函数。**

****语法:****

```scala
def this(......)
```

****要点:****

*   **在单个程序中，我们可以创建多个辅助构造函数，但是它们有不同的签名或参数列表。**
*   **每个辅助构造函数必须调用一个先前定义的构造函数。**
*   **调用构造函数可以是一个主构造函数或另一个辅助构造函数，它以文本形式出现在调用构造函数之前。**
*   **辅助构造函数的第一条语句必须包含使用**这个**的构造函数调用。**

****示例:****

## **斯卡拉**

```scala
// Scala program to illustrate the
// concept of Auxiliary Constructor

// Primary constructor
class GFG( Aname: String, Cname: String)
{
    var no: Int = 0;;
    def display()
    {
        println("Author name: " + Aname);
        println("Chapter name: " + Cname);
        println("Total number of articles: " + no);

    }

    // Auxiliary Constructor
    def this(Aname: String, Cname: String, no:Int)
    {

        // Invoking primary constructor
        this(Aname, Cname)
        this.no=no
    }
}

object Main
{
    def main(args: Array[String])
    {

        // Creating object of GFG class
        var obj = new GFG("Anya", "Constructor", 34);
        obj.display();
    }
}
```

****输出:****

```scala
Author name: Anya
Chapter name: Constructor
Total number of articles: 34
```