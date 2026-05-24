# 斯卡拉|特征

> 原文:[https://www.geeksforgeeks.org/scala-traits/](https://www.geeksforgeeks.org/scala-traits/)

特性就像 Java 中的[接口](https://www.geeksforgeeks.org/interfaces-in-java/)。但是它们比 Java 中的接口更强大，因为在特性中，您可以实现成员。**特征**可以有方法(抽象和非抽象)和字段作为其成员。

<center>**斯卡拉特质的几个要点。**</center>

*   Traits are created using *trait* keywords.
    **Syntax:**

    ```scala
    trait Trait_Name{
    // Fields..
    // Methods..
    }
    ```

    **示例:**

    ```scala
    // Scala program to illustrate how to 
    // create traits

    // Trait 
    trait MyTrait
    {
        def pet 
        def pet_color
    }

    // MyClass inherits trait
    class MyClass extends MyTrait
    {

        // Implementation of methods of MyTrait
        def pet()
        {
            println("Pet: Dog")
        }

        def pet_color()
        {
            println("Pet_color: White")
        }

        // Class method
        def pet_name()
        {
            println("Pet_name: Dollar")
        }
    } 

    object Main 
    {

        // Main method
        def main(args: Array[String]) 
        {
            val obj = new MyClass();
            obj.pet();
            obj.pet_color();
            obj.pet_name();
        }
    }
    ```

    **输出:**

    ```scala
    Pet: Dog
    Pet_color: White
    Pet_name: Dollar

    ```

*   在 Scala 中，我们被允许在特征中实现方法(只有抽象方法)。如果一个特征包含方法实现，那么扩展这个特征的类不需要实现已经在特征中实现的方法。如下例所示。
    **例:**

```scala
// Scala program to illustrate the concept of
// abstract and non-abstract method in Traits

// Trait with abstract and non-abstract methods
trait MyTrait
{
    // Abstract method 
    def greeting

    // Non-abstract method
    def tutorial
    {
        println("This is a tutorial" + 
                "of Traits in Scala")
    }
}

// MyClass inherits trait
class MyClass extends MyTrait
{

    // Implementation of abstract method
    // No need to implement a non-abstract 
    // method because it already implemented
    def greeting()
    {
        println("Welcome to GeeksfoGeeks")
    }
} 

object Main
{

    // Main method
    def main(args: Array[String]) 
    {
        val obj = new MyClass();
        obj.greeting
        obj.tutorial
    }
}
```

**输出:**

```scala
Welcome to GeeksfoGeeks
This is a tutorial of Traits in Scala

```

*   Traits 不包含构造函数参数。*   当一个类继承一个特性时，使用*扩展*关键字。
    **语法:**

    ```scala
    class Class_Name extends Trait_Name{
    // Code..
    }
    ```

    *   When a class inherits multiple traits then use *extends* keyword before the first trait and after that use *with* keyword before other traits. As shown in the below example.
    **Syntax:**

    ```scala
    class Class_Name extends Trait_Name1 with Trait_Name2 with Trait_Name3{
    // Code..
    }
    ```

    **示例:**

    ```scala
    // Scala program to illustrate how
    // a class inherits multiple traits

    // Trait 1
    trait MyTrait1
    {

        // Abstract method 
        def greeting

    }

    //Trait 2
    trait MyTrait2
    {

        // Non-abstract method
        def tutorial
        {
            println("This is a tutorial" + 
                   "of Traits in Scala")
        }
    }

    // MyClass inherits multiple traits
    class MyClass extends MyTrait1 with MyTrait2
    {

        // Implementation of abstract method
        def greeting()
        {
            println("Welcome to GeeksfoGeeks")
        }
    } 

    object Main 
    {

        // Main method
        def main(args: Array[String]) 
        {
            val obj = new MyClass();
            obj.greeting
            obj.tutorial
        }
    }
    ```

    **输出:**

    ```scala
    Welcome to GeeksfoGeeks
    This is a tutorial of Traits in Scala

    ```

    *   抽象类也可以通过使用*扩展*关键字来继承特征。
    **语法:**

    ```scala
    abstract class Class_name extends Trait_Name{
    // code..
    }
    ```

    *   在 Scala 中，一个特征可以通过使用*扩展*关键字来继承另一个特征。
    **语法:**

    ```scala
    trait Trait_Name1 extends Trait_Name2{
    // Code..
    }
    ```

    *   性状支持多重遗传。*   在 Scala 中，一个类既可以继承普通类，也可以继承抽象类和特征，方法是在类名前使用*扩展*关键字，在特征名前使用*扩展*关键字。
    **语法:**

    ```scala
    class Class_Name1 extends Class_Name2 with Trait_Name{
    // Code..
    } 
    ```

    *   In Traits, abstract fields are those fields with containing initial value and concrete fields are those fields which contain the initial value. we are allowed to override them in the class which extends trait. If a field is declared using the *var* keyword, then there is no need to write *override* keyword when we override them. And if a field is declared using the *val* keyword, then you must write *override* keyword when we override them.
    **Example:**

    ```scala
    // Scala program to illustrate 
    // concrete and abstract fields in traits

    trait MyTrait
    {

        // Abstract field
        var value: Int 

        // Concrete field
        var Height = 10
        val Width = 30
    }

    class MyClass extends MyTrait
    {

        // Overriding MyTrait's fields
        var value = 12
        Height = 40
        override val Width = 10

        // Method to display the fields
        def Display()
        {
            printf("Value:%d", value);
            printf("\nHeight:%d" ,Height);
            printf("\nWidth:%d", Width);
        }
    }

    object Main
    {

        // Main method
        def main(args: Array[String])
        {
            val obj = new MyClass();
            obj.Display();
        }
    }
    ```

    **输出:**

    ```scala
    Value:12
    Height:40
    Width:10
    ```

    *   We can also add traits to an object instance. Or in other words, We can directly add a trait in the object of a class without inheriting that trait into the class. We can add a trait in the object instance by using *with* keyword.
    **Syntax:**

    ```scala
    val object_name = new Class_name with Trait_Name;
    ```

    **示例:**

    ```scala
    // Scala program to illustrate how 
    // to add a trait to an object instance 

    class MyClass{}
    trait MyTrait
    {
        println("Welcome to MyTrait");
    }
    object Main 
    {

        // Main method
        def main(args: Array[String])
        {

            // Here MyTrait is added to the 
            // object instance of MyClass
            val obj = new MyClass with MyTrait;
        }
    }
    ```

    **输出:**

    ```scala
    Welcome to MyTrait
    ```