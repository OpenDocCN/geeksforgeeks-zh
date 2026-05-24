# Scala 中的λ表达

> 原文:[https://www.geeksforgeeks.org/lambda-expression-in-scala/](https://www.geeksforgeeks.org/lambda-expression-in-scala/)

**Lambda 表达式**是指使用[匿名函数](https://www.geeksforgeeks.org/anonymous-functions-in-scala/)代替变量或值的表达式。当我们有一个简单的函数在一个地方使用时，Lambda 表达式更方便。这些表达式比定义整个函数更快、更有表现力。我们可以使我们的 lambda 表达式*可重用*用于任何类型的转换。它可以迭代对象集合，并对它们执行某种转换。
**语法**:

```scala
val lambda_exp = (variable:Type) => Transformation_Expression
```

**例**:

```scala
// lambda expression to find double of x
val ex = (x:Int) => x + x
```

**Working With Lambda Expressions**

*   We can pass values to a lambda just like a normal function call.
    **Example :**

    ```scala
    // Scala program to show
    // working of lambda expression

    // Creating object
    object GfG
    {

    // Main method
    def main(args:Array[String])
    { 
        // lambda expression
        val ex1 = (x:Int) => x + 2

        // with multiple parameters
        val ex2 = (x:Int, y:Int) => x * y

        println(ex1(7))
        println(ex2(2, 3))
    }
    }
    ```

    **输出:**

    ```scala
    9
    6
    ```

*   要对任何集合应用变换，我们一般使用 **map()** 函数。这是一个高阶函数，我们可以将 lambda 作为参数传递，以便根据 lambda 表达式的定义转换集合中的每个元素。
    T3】例:

```scala
// Scala program to apply
// transformation on collection

// Creating object
object GfG
{

// Main method
def main(args:Array[String])
{
    // list of numbers
    val l = List(1, 1, 2, 3, 5, 8)

    // squaring each element of the list
    val res = l.map( (x:Int) => x * x )

/* OR
val res = l.map( x=> x * x )
*/
    println(res)
}
}
```

**输出:**

```scala
List(1, 1, 4, 9, 25, 64)
```

我们可以看到，执行平方运算的匿名函数是不可重用的。

*   We are passing it as an argument. However, we can make it reusable and may use it with different collections.
    **Example :**

    ```scala
    // Scala program to apply
    // transformation on collection

    // Creating object
    object GfG
    {
        // Main method
        def main(args:Array[String])
        {
            // list of numbers
            val l1 = List(1, 1, 2, 3, 5, 8)
            val l2 = List(13, 21, 34)

            // reusable lambda
            val func = (x:Int) => x * x

            // squaring each element of the lists
            val res1 = l1.map( func )
            val res2 = l2.map( func )

            println(res1)
            println(res2)
        }
    }
    ```

    **输出:**

    ```scala
    List(1, 1, 4, 9, 25, 64)
    List(169, 441, 1156)
    ```

    *   A lambda can also be used as a parameter to a function.
    **Example :**

    ```scala
    // Scala program to pass lambda
    // as parameter to a function

    // Creating object
    object GfG
    {

        // transform function with integer x and 
        // function f as parameter
        // f accepts Int and returns Double
        def transform( x:Int, f:Int => Double) 
        =
        f(x)

        // Main method
        def main(args:Array[String])
        {

            // lambda is passed to f:Int => Double
            val res = transform(2, r => 3.14 * r * r)

            println(res)
    }
    }
    ```

    **输出:**

    ```scala
    12.56
    ```

    在上例中，**转换**函数接受整数 x 和函数 f，将转换应用于 f 定义的 x。在函数调用中作为参数传递的 Lambda 返回 **Double** 类型。因此，参数 *f* 必须服从λ定义。

    *   We can perform the same task on any collection as well. In case of collections, the only change we need to make in transform function is using **map** function to apply transformation defined by *f* to every element of the list *l*.
    **Example :**

    ```scala
    // Scala program to pass lambda
    // as parameter to a function

    // Creating object
    object GfG
    {

        // transform function with integer list l and 
        // function f as parameter
        // f accepts Int and returns Double
        def transform( l:List[Int], f:Int => Double) 
        =
        l.map(f)

        // Main method
        def main(args:Array[String])
        {
            // lambda is passed to f:Int => Double
            val res = transform(List(1, 2, 3), r => 3.14 * r * r)
            println(res)
        }
    }
    ```

    **输出:**

    ```scala
    List(3.14, 12.56, 28.259999999999998)
    ```