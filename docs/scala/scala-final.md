# Scala | Final

> 原文:[https://www.geeksforgeeks.org/scala-final/](https://www.geeksforgeeks.org/scala-final/)

在 Scala 中， **Final** 是一个关键字，用于通过各种方式对超类或父类施加限制。我们可以将 final 关键字与变量、方法和类一起使用。
以下是 Scala

***   How to use the final keyword in Scala Final variable:**

Scale final 变量在整个程序中声明并作为常量使用时只初始化一次。在下面的例子中，变量**区域**是最终的，它被声明为最终的，并且在*超类* **形状**中声明时也被初始化。如果我们想从派生类 Rectangle 中访问或修改变量区域，那么这是不可能的，因为变量区域的限制是由关键字 final 添加的。

Scala 最终变量通过以下方式初始化:

*   同时声明
*   在静态块中
*   在构造函数中

## 斯卡拉

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

Following error occurs while running above code

**输出:**

```scala

prog.scala:5: error: overriding value area in class Shapes of type Int;
 value area cannot override final member
override val area:Int = 100
             ^
one error found

```

*   **Scala Final Methods:
    Final method *CalArea* in the parent class (Shapes) indicate that, method cannot override in a child class (Rectangle).

    ## 斯卡拉

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

    Following error occurs while running above code

    **输出:**

    ```scala
    prog.scala:8: error: overriding method CalArea in class Shapes of type ()Unit;
     method CalArea cannot override final member
        override def CalArea(){
                         ^
    one error found

    ```** *   ****Scala Final Classes
    If the class in Scala is final then it cannot inherit to derived class. Inheritance restriction will be added by final keyword. Here if class Shapes are final then its all members also final and cannot used in derived class.

    ## 斯卡拉

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

    Following error occurs while running above code

    **输出:**

    ```scala

    prog.scala:4: error: illegal inheritance from final class Shapes
    class Rectangle extends Shapes{
                            ^
    one error found

    ```****