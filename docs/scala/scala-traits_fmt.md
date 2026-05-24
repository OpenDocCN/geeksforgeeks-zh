# Scala 特征

> 原文: [https://www.geeksforgeeks.org/scala-traits/](https://www.geeksforgeeks.org/scala-traits/)

特性就像 Java 中的[接口](https://www.geeksforgeeks.org/interfaces-in-java/)。但是它们比 Java 中的接口更强大，因为在特性中，您可以实现成员。特征可以有方法（抽象和非抽象）和字段作为其成员。

## Scala 特征的几个要点

*   特征使用 `trait` 关键字创建。
    **语法:**

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

*   在 Scala 中，我们被允许在特征中实现方法（只有抽象方法）。如果一个特征包含方法实现，那么扩展这个特征的类不需要实现已经在特征中实现的方法。如下例所示。
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

*   特征不包含构造函数参数。
*   当一个类继承一个特性时，使用 `extends` 关键字。
    **语法:**

    ```scala
    class Class_Name extends Trait_Name{
        // Code..
    }
    ```

*   当一个类继承多个特性时，在第一个特性前使用 `extends` 关键字，在其他特性前使用 `with` 关键字。如下例所示。
    **语法:**

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

*   抽象类也可以通过使用 `extends` 关键字来继承特征。
    **语法:**

    ```scala
    abstract class Class_name extends Trait_Name{
        // code..
    }
    ```

*   在 Scala 中，一个特征可以通过使用 `extends` 关键字来继承另一个特征。
    **语法:**

    ```scala
    trait Trait_Name1 extends Trait_Name2{
        // Code..
    }
    ```

*   特征支持多重继承。
*   在 Scala 中，一个类既可以继承普通类，也可以继承抽象类和特征，方法是在类名前使用 `extends` 关键字，在特征名前使用 `with` 关键字。
    **语法:**

    ```scala
    class Class_Name1 extends Class_Name2 with Trait_Name{
        // Code..
    }
    ```

*   在特征中，抽象字段是那些不包含初始值的字段，具体字段是那些包含初始值的字段。我们可以在继承特征的类中覆盖它们。如果一个字段使用 `var` 关键字声明，那么覆盖时不需要写 `override` 关键字。如果一个字段使用 `val` 关键字声明，那么覆盖时必须写 `override` 关键字。
    **示例:**

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

*   我们也可以将特征添加到对象实例中。换句话说，我们可以直接在类的对象中添加一个特征，而无需在类中继承该特征。我们可以使用 `with` 关键字在对象实例中添加特征。
    **语法:**

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