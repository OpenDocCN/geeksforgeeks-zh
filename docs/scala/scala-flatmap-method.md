# Scala | flatMap 方法

> 原文:[https://www.geeksforgeeks.org/scala-flatmap-method/](https://www.geeksforgeeks.org/scala-flatmap-method/)

在 Scala 中， **flatMap()** 方法与 [*map()方法*](https://www.geeksforgeeks.org/scala-map-method/) 相同，唯一不同的是在 *flatMap* 中，删除了一个项目的内部分组，生成了一个序列。可以定义为*贴图*方法和*展平*方法的混合。运行*贴图*方法后运行*展平*方法得到的输出与*平面贴图()*得到的输出相同。因此，我们可以说 *flatMap* 首先运行 *map* 方法，然后运行*flat*方法来生成期望的结果。
**注:**

*   它有一个内置的*选项*类，作为一个选项，可以表示为一个最多有一个元素的序列，即要么是空的，要么只有一个元素。
*   flat()方法用于分解 Scala 集合的元素，以便用相似类型的元素构建一个集合。

让我们看一个例子来说明*平面图*是如何工作的。

```scala
val name = Seq("Nidhi", "Singh")

```

**案例 1:**
让我们在所述序列上应用 map()和 let()。

> //应用 map()
> val result1 = name.map(_。toLowerCase)
> 
> //输出
> 列表(尼迪、辛格)
> 
> //现在应用展平()，值
> 结果 2 =结果 1 .展平
> 
> //输出
> 列表(n，I，d，h，I，s，I，n，g，h)

**案例 2:**
让我们直接在给定的序列上应用 flatMap()。

```scala
name.flatMap(_.toLowerCase)

// Output
List(n, i, d, h, i, s, i, n, g, h)

```

所以，我们在这里可以看到两种情况下得到的输出是一样的因此，我们可以说 *flatMap* 是 *map* 和*flat*方法的组合。
现在来看一些 *flatMap* 方法的例子。

*   Utilizing *flatMap* on a sequence of Strings.
    **Example:**

    ```scala
    // Scala program of flatMap

    // Creating object
    object GfG
    { 

        // Main method
        def main(args:Array[String])
        {

            // Creating a sequence of strings
            val portal = Seq("Geeks", "for", "Geeks")

            // Applying flatMap
            val result = portal.flatMap(_.toUpperCase)

            // Displays output
            println(result)

        }
    }
    ```

    **Output:**

    ```scala
    List(G, E, E, K, S, F, O, R, G, E, E, K, S)

    ```

    这里，*平面图*被应用于所述序列，因此，产生字符序列的列表。

*   Applying *flatMap* with another functions.
    **Example :**

    ```scala
    // Scala program of flatMap

    // Creating object
    object GfG
    { 

        // Main method
        def main(args:Array[String])
        {

            // Creating a list of numbers
            val list = List(2, 3, 4)

            // Defining a function
            def f(x:Int) = List(x-1, x, x+1)

            // Applying flatMap
            val result = list.flatMap(y => f(y))

            // Displays output
            println(result)

        }
    }
    ```

    **Output:**

    ```scala
    List(1, 2, 3, 2, 3, 4, 3, 4, 5)

    ```

    这里，*平面图*应用于程序中定义的另一个函数，因此生成了一个数字序列列表。让我们看看输出是如何计算的。

    ```scala
    List(List(2-1, 2, 2+1), List(3-1, 3, 3+1), List(4-1, 4, 4+1))

    // After evaluation we get,
    List(List(1, 2, 3), List(2, 3, 4), List(3, 4, 5))

    ```

    因此，第一步的工作就像在所述的另一个函数上应用*映射*方法。

    ```scala
    List(1, 2, 3, 2, 3, 4, 3, 4, 5)

    ```

    第二步的工作方式类似于将*展平*应用于第一步通过 map 方法获得的输出。
    T3】例:

    ```scala
    // Scala program of flatMap

    // Creating object
    object GfG
    { 

        // Main method
        def main(args:Array[String])
        {

            // Creating a sequence of numbers
            val seq = Seq(4, 5, 6, 7)

            // Applying flatMap on another
            // function
            val result = seq flatMap { s =>
                            Seq(s, s-1)
            }

            // Displays output
            println(result)

        }
    }
    ```

    **Output:**

    ```scala
    List(4, 3, 5, 4, 6, 5, 7, 6)

    ```

    这里，也获得了类似于具有另一功能的*平面图*的第一示例的输出。

*   Utilizing *flatMap* on if-else statements.
    **Example :**

    ```scala
    // Scala program of flatMap

    // Creating object
    object GfG
    { 

        // Main method
        def main(args:Array[String])
        {

            // Creating a sequence of numbers
            val seq = Seq(8, 15, 22, 23, 24)

            // Applying flatMap on if-else
            // statement
            val result = seq flatMap { s =>
                    if (s % 3 == 0) Seq(s)
                    else Seq(-s)
            }

            // Displays output
            println(result)
        }
    }
    ```

    **Output:**

    ```scala
    List(-8, 15, -22, -23, 24)

    ```

    这里，如果给定序列的一个元素满足所述条件，则返回该元素，否则获得该元素的负值。