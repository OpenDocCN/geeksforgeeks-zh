# Scala |下界

> 原文:[https://www.geeksforgeeks.org/scala-lower-bound/](https://www.geeksforgeeks.org/scala-lower-bound/)

**类型界限**基本上是对参数或变量的一种限制。通过使用这些类型界限，我们可以设置变量的限制。这些界限有助于将我们的代码放入真实世界的例子中。我们需要对现实生活中的每个因素施加一定的限制和界限，这就是 Scala 中类型界限的作用。

主要有两种类型的类型界限:

*   上限类型*   Lower type Bound

    在本节中，我们将更加关注下限。**类型下限**用于声明另一个类型的超类型。下限用 **> :** 表示。任何下限语句都可以写成**'>:S】'**。这里 T 是类型参数，S 是类型。上述下界声明意味着类型参数 T 必须与超类型 S 的 S 相同

    让我们理解超类型，假设我们写 S>:T，那么这个下界语句总是有等于 S 或小于 S 的 T，这意味着在这种情况下 T 是有界的。所以我们可以说 T 是 s 的超类型。

    **语法:**

    ```scala
    [T >: Demo[T]]
    ```

    在上面的例子中，我们定义了从类型参数 T 到类型演示的下限。并且必须是演示或演示类型的超类型。

    **我们再举一个例子**
    如果我以如下所示的某种格式声明所有的类:

    ```scala
    trait Food
    class eatables extends Food
    class drinks extends Food
    class fruits extends eatables
    class vegetables extends eatables
    class cold_drinks extends drinks
    class hot_drinks extends drinks

    class position[A](val place:A) 

    ```

    现在所有的类和子类都已经用上面的语句声明了。所以如果我们考虑语句位置[A]，这里位置是泛型，A 是抽象类型。这可以进一步简化，位置[A]表示传递到位置所需的值必须是类型 A。这意味着如果我给出一个命令位置[水果]，那么它将使用水果的实例来创建。为了检验这一点，我们将看到一个例子:

    ```scala
    new position[fruits](new fruits)
    new position[fruits](new drinks)
    new position[eatables](new vegetables)
    ```

    在上面给出的例子中，我们将注意到第一条语句将被编译，但是第二条语句将显示错误，因为水果和饮料不是同一类型的。另一方面，第三个语句将被编译，因为蔬菜是食物的子类型。现在在上面给出的语句中使用一些下限命令:

    ```scala
    class position[A >: fruits](val place=A)
    ```

    通过这种说法，我们可以说，我们可以定位任何超类型的水果，这意味着食品和食品。因此，通过这一点，我们可以明确地看到，如果对任何真实世界的例子使用一些逻辑，Scala 的下限都是非常有用和适用的。因此，我们可以将所有现实生活中的限制和约束加到我们在编码语言中使用的变量上。

    **示例:**

    ```scala
    // Scala Program To Demonstrate Scala Lower Bound
    class GeeksforGeeks
    class Author extends GeeksforGeeks
    class Geeks extends GeeksforGeeks

    class ComputerSciencePortal
    {
        // Declaration of Lower bound
        def display [T >: Geeks](d : T)
        {
            println(d)
        }
    }

    // Object created
    object ScalaUpperBounds
    {
        // Driver code
        def main(args: Array[String])
        {

            val geeksforgeeks = new GeeksforGeeks
            val author = new Author
            val geeks = new Geeks

            val computerscienceportal = new ComputerSciencePortal

            computerscienceportal.display(geeksforgeeks)
            computerscienceportal.display(geeks)
            computerscienceportal.display(author)
        }
    }
    ```

    **Output:**

    ```scala
    GeeksforGeeks@506e1b77
    Geeks@4fca772d
    Author@9807454

    ```

    这里，下界是在类 ComputerSciencePortal 中定义的，GeeksforGeeks 是作者的超级类。它在下限被接受。

    ```scala
    // Scala Program To Demonstrate Scala Lower Bound
    class Principal
    class Teacher extends Principal
    class Student extends Teacher

    class School
    {
        // Declaration of lower bound
        def display [T >: Teacher](t: T)
        {
            println(t)
        }
    }

    // Object created
    object ScalaUpperBounds
    {
        // Driver code
        def main(args: Array[String])
        {
            // Defined new variable
            val principal = new Principal
            val teacher = new Teacher
            val student = new Student

            val school = new School

            school.display(principal)
            school.display(teacher)
            school.display(student)
    }
    }
    ```

    **Output:**

    ```scala
    Principal@506e1b77
    Teacher@4fca772d
    Student@9807454

    ```

    这里我们定义了 Class School 中的下界，即[T >:教师]，这意味着显示方法接受 Principal 类对象或其子类(即教师)或教师类子类(即学生)，这意味着将接受教师的超类。