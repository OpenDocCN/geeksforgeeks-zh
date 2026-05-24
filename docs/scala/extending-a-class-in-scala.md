# 在 Scala 中扩展一个类

> 原文:[https://www.geeksforgeeks.org/extending-a-class-in-scala/](https://www.geeksforgeeks.org/extending-a-class-in-scala/)

**在 Scala 中扩展类**用户可以设计一个继承类。为了在 Scala 中扩展一个类，我们使用了 extends 关键字。在 Scala 中扩展一个类有两个限制:

*   要重写 scala 中的方法，override 关键字是必需的。
*   Only the primary constructor can pass parameters to the base constructor.

    **语法:**

    ```scala
    class base_class_name extends derived_class_name
    {
        // Methods and fields
    }

    ```

    **示例:**

    ```scala
    // Scala program of extending a class

    // Base class 
    class Geeks1
    { 
        var Name: String = "chaitanyashah"
    } 

    // Derived class 
    // Using extends keyword 
    class Geeks2 extends Geeks1
    { 
        var Article_no: Int = 30

        // Method 
        def details() 
        { 
            println("Author name: " + Name); 
            println("Total numbers of articles: " + Article_no); 
        } 
    } 

    // Creating object
    object GFG 
    { 

        // Driver code 
        def main(args: Array[String]) 
        { 

            // Creating object of derived class 
            val ob = new Geeks2(); 
            ob.details(); 
        } 
    } 
    ```

    **输出:**

    ```scala
    Author name: chaitanyashah
    Total numbers of articles: 30

    ```

    在上面的例子中 **Geeks1** 是*基类*， **Geeks2** 是*派生类*，它是使用 extends 关键字从 Geeks1 派生的。在主方法中，当我们创建 Geeks2 类的对象时，基类的所有方法和字段的副本都会在该对象中获取内存。这就是为什么通过使用派生类的对象，我们也可以访问基类的成员。

    **示例:**

    ```scala
    // Scala program of extending a class

    // Base class
    class Parent 
    { 
        var Name1: String = "geek1"
        var Name2: String = "geek2"
    } 

    // Derived from the parent class 
    class Child1 extends Parent 
    { 
        var Age: Int = 32
        def details1() 
        { 
            println(" Name: " + Name1)
            println(" Age: "  + Age) 
        } 
    } 

    // Derived from Parent class 
    class Child2 extends Parent 
    { 
        var Height: Int = 164

        // Method 
        def details2() 
        { 
            println(" Name: " + Name2) 
            println(" Height: " + Height) 
        } 
    } 

    // Creating object
    object GFG 
    { 

        // Driver code 
        def main(args: Array[String]) 
        { 

            // Creating objects of both derived classes 
            val ob1 = new Child1(); 
            val ob2 = new Child2(); 
            ob1.details1(); 
            ob2.details2(); 
        } 
    } 
    ```

    **输出:**

    ```scala
    Name: geek1
    Age: 32
    Name: geek2
    Height: 164

    ```

    在上例中 **Parent** 是*基类* **Child1** 和 **Child2** 是*派生类*，它是使用 extends 关键字从 Parent 派生的。在主方法中，当我们创建 Child1 和 Child2 类的对象时，基类的所有方法和字段的副本都会在这个对象中获取内存。
    **示例:**

    ```scala
    // Scala program of extending a class

    // Base class
    class Bicycle (val gearVal:Int, val speedVal: Int)
    {
        // the Bicycle class has two fields 
       var gear: Int = gearVal
       var speed: Int = speedVal

       // the Bicycle class has two methods 
       def applyBreak(decrement: Int)
       {
           gear = gear - decrement
           println("new gear value: " + gear);
       }
       def speedUp(increment: Int)
       {
           speed = speed + increment;
           println("new speed value: " + speed);
       }
    }

    // Derived class
    class MountainBike(override val gearVal: Int, 
                        override val speedVal: Int,
                        val startHeightVal : Int) 
                        extends Bicycle(gearVal, speedVal)
    {
        // the MountainBike subclass adds one more field 
       var startHeight: Int = startHeightVal

       // the MountainBike subclass adds one more method 
       def addHeight(newVal: Int)
       {
           startHeight = startHeight + newVal
           println("new startHeight : " + startHeight);
       }
    }

    // Creating object
    object GFG 
    {
        // Main method
        def main(args: Array[String]) 
        {
            val bike = new MountainBike(10, 20, 15);

            bike.addHeight(10);
            bike.speedUp(5);
            bike.applyBreak(5);
        }
    }
    ```

    **输出:**

    ```scala
    new startHeight : 25
    new speed value: 25
    new gear value: 5

    ```

    在上面的程序中，当一个登山自行车类的对象被创建时，超类的所有方法和字段的副本在这个对象中获得内存。