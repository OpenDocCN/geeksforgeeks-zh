# Scala |重复方法参数

> 原文:[https://www . geesforgeks . org/Scala-repeated-method-parameters/](https://www.geeksforgeeks.org/scala-repeated-method-parameters/)

在 Scala 中，支持**重复方法参数**，当我们不知道一个方法需要多少参数时，这很有帮助。Scala 的这一特性用于将无限的参数传递给定义的方法。
**要点:**

*   具有*重复参数*的方法应该具有相同类型的每个参数。
*   A *重复参数*始终是定义方法的最后一个参数。
*   我们定义的方法，只能有一个参数作为*重复参数*。

**示例:**

```scala
// Scala program of repeated 
// parameters

// Creating object
object repeated
{

    // Main method
    def main(args: Array[String])
    {

        // Creating a method with
        // repeated parameters
        def add(x: Int*)
        : Int =
        {

            // Applying 'fold' method to 
            // perform binary operation
            x.fold(0)(_+_)

        }

        // Displays Addition
        println(add(2, 3, 5, 9, 6, 10, 11, 12))
    }
}
```

**Output:**

```scala
58

```

为了添加任意数量的额外参数，我们需要在正在使用的参数类型后面加上 ***** 标记。
**重复参数的更多例子:**

*   可以在重复参数方法中传递数组。
    **例:**

```scala
// Scala program of repeated 
// parameters

// Creating object
object arr
{

    // Main method
    def main(args: Array[String])
    {

        // Creating a method with
        // repeated parameters
        def mul(x: Int*)
        : Int =
        {

            // Applying 'product' method to 
            // perform multiplication
            x.product

        }

        // Displays product
        println(mul(Array(7, 3, 2, 10): _*))
    }
}
```

**Output:**

```scala
420

```

为了在已定义的方法中传递数组，我们需要在传递数组中的值后放一个冒号即 **:** 和 **_*** 标记。

*   An example to show that Repeated Parameters are always the last parameter of the method defined.
    **Example:**

    ```scala
    // Scala program of repeated 
    // parameters

    // Creating object
    object str
    {

        // Main method
        def main(args: Array[String])
        {

            // Creating a method with
            // repeated parameters
            def show(x: String, y: Any*) =
            {

                // using 'mkString' method to
                // convert a collection to a
                // string with a separator
                "%s is a %s".format(x, y.mkString("_"))
            }

            // Displays string 
            println(show("GeeksforGeeks", "Computer",
                                "Sciecne", "Portal"))
        }
    }
    ```

    **Output:**

    ```scala
    GeeksforGeeks is a Computer_Sciecne_Portal

    ```

    这里**格式**用来格式化字符串。