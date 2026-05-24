# 刻度|混合线

> 原文:[https://www.geeksforgeeks.org/scala-trait-mixins/](https://www.geeksforgeeks.org/scala-trait-mixins/)

我们可以用一个类或一个抽象类来扩展几个标量特征，这个抽象类被称为 T2 特征融合子。值得知道的是，只有特质或特质与类的交融或特质与抽象类的交融才能被我们延展。这里甚至必须保持特征序列*混合*否则编译器会抛出一个错误。
**注:**

1.  在组成一个类时使用了 Mixins 特性。
2.  一个类很难有一个超类，但它可以有无数个特征混合。超级类和特性 Mixins 可能有相同的超级类型。

现在，让我们看一些例子。

*   Extending abstract class with trait
    **Example :**

    ```scala
    // Scala program of trait Mixins

    // Trait structure
    trait Display
    { 

        def Display() 
    } 

    // An abstract class structure
    abstract class Show
    { 
        def Show() 
    } 

    // Extending abstract class with
    // trait
    class CS extends Show with Display
    {

        // Defining abstract class
        // method
        def Display()
        {     
            // Displays output
            println("GeeksforGeeks") 
        } 

        // Defining trait method
        def Show()
        {                                     
            // Displays output 
            println("CS_portal") 
        } 
    }

    // Creating object
    object GfG
    { 
        // Main method
        def main(args:Array[String])
        { 

            // Creating object of class CS
            val x = new CS() 

            // Calling abstract method
            x.Display() 

            // Calling trait method
            x.Show() 
        } 
    } 
    ```

    **Output:**

    ```scala
    GeeksforGeeks
    CS_portal

    ```

    在这里，Mixins 的正确顺序是，我们需要先扩展任意类或抽象类，然后用关键字 ***和*** 扩展任意性状。

*   Extending abstract class without trait
    **Example :**

    ```scala
    // Scala program of trait Mixins

    // Trait structure
    trait Text
    { 
        def txt() 
    }

    // An abstract class structure
    abstract class LowerCase
    { 
        def lowerCase() 
    } 

    // Extending abstract class 
    // without trait
    class Myclass extends LowerCase
    {

        // Defining abstract class
        // method
        def lowerCase()
        { 
            val y = "GEEKSFORGEEKS"

            // Displays output
            println(y.toLowerCase()) 
        } 

        // Defining trait method
        def txt()
        {                                     

            // Displays output 
            println("I like GeeksforGeeks") 
        } 
    } 

    // Creating object
    object GfG
    { 
        // Main method
        def main(args:Array[String])
        { 

            // Creating object of 'Myclass'
            // with trait 'Text'
            val x = new Myclass() with Text

            // Calling abstract method
            x.lowerCase() 

            // Calling trait method
            x.txt() 
        } 
    } 
    ```

    **Output:**

    ```scala
    geeksforgeeks
    I like GeeksforGeeks

    ```

    因此，从这个例子中，我们可以说这种特性甚至可以在创建对象时扩展。
    **注意:**如果我们先扩展一个特性，然后扩展抽象类，那么编译器会抛出一个错误，因为这不是特性 Mixins 的正确顺序。