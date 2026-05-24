# Scala |方差

> 原文:[https://www.geeksforgeeks.org/scala-variances/](https://www.geeksforgeeks.org/scala-variances/)

**变异**是复杂类型或其组成类型的子类型关系的相互联系。*方差*解释了具有*参数*或*参数*的类型的遗传相关性。这些类型属于*泛型*类，它接受一个像参数一样的类型。在存在差异的情况下，我们可以在复杂的类型之间创建关系，而在没有差异的情况下，我们将无法重复抽象类。Scala 差异有三种类型，如下所示:

1.  协变的
2.  逆变的
3.  不变的

**一些要点:**

*   在 Scala 中，集合的类型可以通过方差更安全地构造。
*   差异可以为我们提供一些额外的可调整的进步。
*   它还有助于开发真实的应用程序。
*   差异可以应用于任何标量类型，如列表、集合等。

**Types of Variances**

让我们详细讨论每种类型。

*   **Covariant:** If a generic class has a type parameter T, then its Covariant notation will be [+T]. Suppose, we have two List types of Scala i.e, S and T. where, S is sub-type of T, then you can say that List[S] is also the sub-type of List[T]. If two types are related like this then they fall under the Covariant type. List[T] can be called as *Generic*.
    **Syntax:**

    ```scala
    List[+T]
    ```

    这里， **T** 是类型参数， **+** 是协方差的符号。
    **例:**

    ```scala
    // Scala program of covariant
    // type

    // Creating an abstract class
    // for Student
    abstract class Student
    {
        def name: String
    }

    // Creating a sub-class Girls
    // of Student
    case class Girls(name: String) extends Student

    // Creating a sub-class Boys
    // of Student
    case class Boys(name: String) extends Student

    // Creating an Object Covariance
    // that inherits main method of
    // App
    object Covariance extends App
    {
        // Creating a method
        def Studentnames(students: List[Student]): Unit =
        {
            students.foreach { student =>

            // Displays students name
            println(student.name)
        }
        }

        // Assigning names 
        val boys: List[Boys] = List(Boys("Kanchan"), Boys("Rahul"))
        val girls: List[Girls] = List(Girls("Nidhi"), Girls("Geeta"))

        // Accessing list of boys
        Studentnames(boys)

        // Accessing list of girls
        Studentnames(girls)
    }
    ```

    **Output:**

    ```scala
    Kanchan
    Rahul
    Nidhi
    Geeta

    ```

    在这里，男孩和女孩的列表都属于学生列表，因为他们是它的子类型，因此，在这里，当调用超级类型学生时，显示所有学生的名称。
    **注:**

    *   抽象类在这里被用来应用协方差，因为它有列表[+T]，其中类型参数 T 是协变的。
    *   这里使用了一个特性*应用程序*来快速地将对象转换成可用的程序。
*   **Contravariant:** If a generic class has a type parameter T, then its Contravariant notation will be [-T]. Suppose, we have two List types of Scala i.e, S and T. where, S is sub-type of T, but List[T] is the sub-type of List[S]. If two types are related like this then they fall under the Contravariant type. It is opposite of covariant.
    **Syntax:**

    ```scala
    List[-T]
    ```

    这里， **T** 是类型参数，**–**是逆变符号。
    **例:**

    ```scala
    // Scala program of Variance of
    // Contravariant type

    // abstract class with a contravariant 
    // type parameter
    abstract class Show[-T] 
    {

        // Method for printing
        // type T
        def print(value: T): Unit
    }

    // A class structure
    abstract class Vehicle
    {
        def name: String
    }

    // Creating sub-class of Vehicle
    case class Car(name: String) extends Vehicle

    // Creating sub-class of class
    // Show
    class VehicleShow extends Show[Vehicle] 
    {
        def print(vehicle: Vehicle): Unit =

        // Displays name of the vehicle
        println("The name of the vehicle is: " + vehicle.name)
    }

    // Creating sub-class of class
    // Show
    class CarShow extends Show[Car] 
    {
        def print(car: Car): Unit =

        // Displays name of the car
        println("The name of the car is: " + car.name)
    }

    // Inheriting main method of 
    // the trait App
    object Contravariance extends App 
    {

        // Assigning value to the name 
        val newCar: Car = Car("Scorpio")

        // Defining a method that
        // prints the name
        def printnewCar(show: Show[Car]): Unit = 
        {
            show.print(newCar)
        }

        // Creating objects
        val showcar: Show[Car] = new CarShow
        val showvehicle: Show[Vehicle] = new VehicleShow

        // Accessing name
        printnewCar(showcar)
        printnewCar(showvehicle)
    }
    ```

    **Output:**

    ```scala
    The name of the car is: Scorpio
    The name of the vehicle is: Scorpio

    ```

    它是逆变式的，所以我们可以用 Show[Vehicle]代替 Show[Car]，这就是为什么 Vehicle 和 Car 返回相同的名称。

*   **Invariant:** In Scala, generic types are by default invariant. Suppose, we have two List types of Scala i.e, S and T. where, S is sub-type of T but List[T] and List[S] are not at all related, then they fall under the invariant type.
    **Syntax:**

    ```scala
    List[T]
    ```

    这里，我们不使用任何符号来表示不变关系。
    **注:**数组【T】、列表缓冲【T】、数组缓冲【T】等类。是可变的，所以它们有不变的类型参数，如果我们在继承关系或子类型中使用不变的类型参数，那么我们会得到一个编译错误。