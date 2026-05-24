# 标量结构

> 原文:[https://www.geeksforgeeks.org/scala-constructs/](https://www.geeksforgeeks.org/scala-constructs/)

一些基本的 Scala 构造是表达式、块、类、对象、函数、方法、特征、主方法、字段和闭包。
**1。Scala 表达式:**Scala 中的可计算语句称为表达式。例如下面是一个表达式: *3 + 4* 。使用 println()打印表达式的输出。
**语法**

```scala
println(expression)
```

**示例**

```scala
// Scala program to illustrate expressions
object Main 
{
    def main(args: Array[String]) 
    {
        println(3)
        println(3 + 4)
        println("Scala")
        println("How " + "are" + " you?") 
    }
}
```

**输出:**

```scala
3
7
Scala
How are you?
```

**2。值:**我们可以用‘val’关键字来命名。这个表达式返回一个结果。
**语法**

```scala
val variable_name = 'Result to be printed'
```

**示例**

```scala
// Scala program to illustrate values
object Main 
{
    def main(args: Array[String]) 
    {
        val name1 ="Arjun"
        println(name1)

        val name2 = "Sheena"
        println(name2)
    }
}
```

**输出**

```scala
Arjun
Sheena
```

这里，这种类型的实体只能有一个值。如果我们试图重新分配该值，那么它将给出错误。

**3。Scala 变量:** [变量](https://www.geeksforgeeks.org/variables-in-scala/)只是一个存储位置，它以其名称为人所知，并存储一些已知和未知的信息，称为值。要声明一个变量，我们使用' var '关键字。
**语法**

```scala
var variable_name = Any_number
```

**例**

```scala
// Scala program to illustrate variables
object Main 
{
    def main(args: Array[String]) 
    {
        // Here, p is a variable
        var p = 3
        p = 4 
        println(p * p) 
    }
}
```

**输出**

```scala
16
```

**4。Scala Block:** 由花括号({})分隔的一组表达式称为块。
**语法**

```scala
println({// Expression})
```

**例**

```scala
// Scala program to illustrate blocks
object Main 
{
    def main(args: Array[String]) 
    {
        println({val p = 10 * 2
                     p + 1}) 
    }
}
```

**输出**

```scala
21
```

**5。Scala 类:**一个[类](https://www.geeksforgeeks.org/class-and-object-in-scala/)是一个用户定义的蓝图或原型，从它可以创建对象。它包含值、变量、类型、类、函数、方法、对象和特征，统称为成员。要声明一个类，我们使用' class '关键字和一个标识符。

**语法**

```scala
{
    class class_name{}
    val variable_name = new class_name
}
```

**例**

```scala
// Scala program to illustrate class

// class 
class Geeks 
{ 

    // Class variable
    var name: String = "GeeksforGeeks"

    // Class method 
    def Show() 
    { 
        println("Company's name : " + name); 
    } 
} 
object Main  
{ 

    // Main method 
    def main(args: Array[String])  
    { 

        // Class object 
        var obj = new Geeks(); 
        obj.Show(); 
    } 
} 
```

**输出:**

```scala
Company's name : GeeksforGeeks
```

**6。对象:** [对象](https://www.geeksforgeeks.org/class-and-object-in-scala/)是它自己的类的单例，即它是它自己的定义的单个实例。
**强:**

```scala
object MyObject{
      def method_name() = {
      // Expression
  }
}
```

**示例:**

```scala
// Scala program to illustrate object
object Main extends App
{
    object MyObject
    {
        def plusthree() = { 
            val x = 2 + 2
            x + 3
        }
    }
    println(MyObject.plusthree) 
}
```

**输出:**

```scala
7
```

**7。Scala Function:** 接受参数的表达式称为函数。或者换句话说，它是执行特定任务的语句的集合。它可以赋给一个变量，这种类型的函数称为匿名函数。= >的左边是参数列表，右边是它将返回的表达式。

**语法**

```scala
(y:Int)=>y+y

```

这个函数接受一个整数参数 y，并返回它的加法。我们也可以给值命名。
**例:**

```scala
// Scala program to illustrate function
object Main 
{
    def main(args: Array[String]) 
    {
        val addition = (y:Int) => y + y
        println(addition(4)) 
    }
}
```

**输出:**

```scala
8

```

**8。Scala 方法:**我们使用关键字“def”定义方法。它几乎类似于一个函数。接下来是标识符、参数列表、返回类型和主体。或者换句话说，它是执行特定任务的语句的集合。
**语法**

```scala
def method_name ([parameter_list]) : [return_type] = {

  // Method body

}
```

**例**

```scala
// Scala program to illustrate method
object Main 
{
    def display()
    {
        println("Welcome to GFG")
    }
    def main(args: Array[String]) 
    {
        // Calling method
        display()
    }
}
```

**输出**

```scala
Welcome to GFG
```

**9。Scala Trait:**[Trait](https://www.geeksforgeeks.org/scala-traits/)就像 Java 中的接口。但是特性允许你实现成员。它可以有方法(抽象的和非抽象的)和字段作为其成员。它是用关键词“特质”来定义的。
**语法**

```scala
trait trait_name
{
// Fields
// Methods
}
```

**例**

```scala
// Scala program to illustrate traits 

// Trait 
trait MyTrait 
{ 
    def show

} 

// MyGfg inherits a trait 
class MyGfg extends MyTrait 
{ 

    // Implementation of methods of MyTrait 
    def show() 
    { 
        println("Hey Geeks") 
    } 

} 

object Main 
{ 

    // Main method 
    def main(args: Array[String]) 
    { 
        val ob = new MyGfg(); 
        ob.show(); 
    } 
} 
```

**输出:**

```scala
Hey Geeks
```

**10。Scala 主方法:**任何程序的入口点都是主方法。JVM 需要一个参数为字符串数组的方法。
**11。字段:**这些字段有助于定义对象状态。它是属于每个对象的一组唯一的实例变量。
**12。闭包:** [闭包](https://www.geeksforgeeks.org/scala-closures/)是一个返回值依赖于其外部声明的变量的函数。