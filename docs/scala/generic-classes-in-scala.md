# Scala 中的泛型类

> 原文:[https://www.geeksforgeeks.org/generic-classes-in-scala/](https://www.geeksforgeeks.org/generic-classes-in-scala/)

在 Scala 中，形成**泛型类**与在 Java 中形成泛型类极其相似。像参数一样接受类型的类被称为 Scala 中的*泛型类*。这个类在方括号内取一个类似参数的类型，即[ ]。在 Scala 中，这些类被明确用于收集类的进度。泛型类型的子类型是不变的，即如果我们有两个列表类型，A 和 B，那么列表[A]是列表[B]的子类型，当且仅当 B 类型相当于 A 类型。
**需要记住的几点:**

*   用于简单类型的类型参数的符号是 *A* ，类似于列表[A]。
*   用于第二、第三、第四等类型参数的符号，泛型类中的类型分别为 *B、C、D、*等。
*   在斯卡拉地图中，用于键的符号是 *A* ，用于值的符号是 *B* 。
*   用于数值的符号是 *N* 。

**注意:**虽然提供了该符号约定，但是类型参数仍然可以使用任何符号。
下面我们来讨论一些例子。
**例:**

```scala
// Scala program of forming 
// Generic classes

// Creating an object
object GfG
{

    // Main method
    def main(args: Array[String]) 
    {

        // Class structure for Generic
        // types 
        abstract class Divide[z] 
        {
            // Defining method 
            def divide(u: z, v: z): z
        }

        // Extending Generic class of 
        // type parameter Int 
        class intDivide extends Divide[Int] 
        {
            // A method returning Int 
            def divide(u: Int, v: Int): Int = u / v
        }

        // Extending Generic Class of 
        // type parameter Double
        class doubleDivide extends Divide[Double] 
        {
            // A method returning Double
            def divide(u : Double, v : Double) : Double = u / v
        }

        // Creating objects and assigning 
        // values to the methods called
        val q = new intDivide().divide(25, 5)
        val r = new doubleDivide().divide(21.0, 5.0)

        // Displays output 
        println(q)
        println(r)

    }
}
```

**Output:**

```scala
5
4.2

```

这里，抽象类 *Divide* 有一个类型参数 *z* ，它存在于方括号中，所以这个类是泛型类型，这个类型参数 *z* 可以占用每一个数据类型。我们定义了一个方法*在泛型类内部划分*，泛型类有两个变量，即 *u* 和 *v* ，这些变量的数据类型为 *z* 。如上所述的类 *intDivide* 采用整数类型，如上所述的类 *doubleDivide* 采用双类型。因此，类型参数 *z* 被 *Int* 和 *Double* 数据类型所取代。通过这种方式，子类型在泛型类中是可能的。

**示例:**

```scala
// Scala program of using generic
// types for numeric values
import Numeric._

// Creating an object
object GfG
{

    // Main method
    def main(args: Array[String]) 
    {

        // Defining generic type for numeric
        // values with implicit parameter 
        def addition[N](a: N, b: N)(implicit num: Numeric[N]):

        // Using a method 'plus' 
        N = num.plus(a, b)

        // Displays the sum of two 
        // numbers
        println("The sum is : "+addition(88, 12))
    }
}
```

**Output:**

```scala
The sum is : 100

```

在这里，我们看到了数值的泛型类型参数，因此，我们在这里使用了符号 *N* ，尽管任何符号都可以用作泛型类型的类型参数。