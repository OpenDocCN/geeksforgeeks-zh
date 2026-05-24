# Scala | Final

> 原文: [https://www.geeksforgeeks.org/scala-final/](https://www.geeksforgeeks.org/scala-final/)

在 Scala 中，`final` 是一个关键字，用于通过各种方式对超类或父类施加限制。我们可以将 `final` 关键字与变量、方法和类一起使用。

## Scala Final Variable

Scala `final` 变量在整个程序中声明并作为常量使用时只初始化一次。在下面的例子中，变量 `area` 是最终的，它被声明为 `final`，并且在超类 `Shapes` 中声明时也被初始化。如果我们想从派生类 `Rectangle` 中访问或修改变量 `area`，那么这是不可能的，因为变量 `area` 的限制是由关键字 `final` 添加的。

Scala 最终变量通过以下方式初始化：
*   同时声明
*   在静态块中
*   在构造函数中

```scala
// Scala program of using final variable
class Shapes
{ 
    // define final variable
    final val area:Int = 60
} 
class Rectangle extends Shapes
{ 
    override val area:Int = 100
    def display()
    { 
        println(area) 
    } 
}

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        var b = new Rectangle() 
        b.display() 
    } 
}
```

运行上述代码会出现以下错误：

**输出:**

```scala
prog.scala:5: error: overriding value area in class Shapes of type Int;
 value area cannot override final member
override val area:Int = 100
             ^
one error found
```

## Scala Final Methods

`final` 方法 `CalArea` 在父类 (`Shapes`) 中表示该方法不能在子类 (`Rectangle`) 中被重写。

```scala
// Scala program of using final method
class Shapes
{ 
    val height:Int = 0
    val width :Int =0

    // Define final method
    final def CalArea(){ 
    } 
} 
class Rectangle extends Shapes
{ 
    override def CalArea()
    { 
        val area:Int = height * width 
        println(area) 
    } 
}

// Creating object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        var b = new Rectangle() 
        b.CalArea() 
    } 
}
```

运行上述代码会出现以下错误：

**输出:**

```scala
prog.scala:8: error: overriding method CalArea in class Shapes of type ()Unit;
 method CalArea cannot override final member
        override def CalArea(){
                         ^
one error found
```

## Scala Final Classes

如果 Scala 中的类是 `final` 的，那么它就不能被派生类继承。`final` 关键字会添加继承限制。这里如果类 `Shapes` 是 `final` 的，那么它的所有成员也是 `final` 的，不能在派生类中使用。

```scala
// Scala program of using final class
final class Shapes
{ 
    // Final variables and functions
    val height:Int = 0
    val width :Int =0
    final def CalArea()
    { 
    } 
} 
class Rectangle extends Shapes
{ 
    // Cannot inherit Shapes class 
    override def CalArea()
    { 
        val area:Int = height * width 
        println(area) 
    } 
}

// Creating Object
object GFG
{ 
    // Main method
    def main(args:Array[String])
    { 
        var b = new Rectangle() 
        b.CalArea()
    } 
}
```

运行上述代码会出现以下错误：

**输出:**

```scala
prog.scala:4: error: illegal inheritance from final class Shapes
    class Rectangle extends Shapes{
                            ^
one error found
```