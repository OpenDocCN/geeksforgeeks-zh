# Scala | Product3

> 原文:[https://www.geeksforgeeks.org/scala-product3/](https://www.geeksforgeeks.org/scala-product3/)

**Product3** 是 Scala 中的一个特质，是三个元素的笛卡尔乘积。这里的线性超类型是*产品*、*等于*、*任意*，这里已知的子类是*图普勒 3* 。它扩展了*产品*的特性，即:

```scala
trait Product3[+T1, +T2, +T3] extends Product
```

其中，T1、T2 和 T3 是 Scala 使用的参数类型。

1.  **抽象价值成员**
    这里的抽象价值成员有:
    *   ```scala
        abstract def _1: T1
        ```

        它返回第一个参数类型的元素。

    *   ```scala
        abstract def _2: T2
        ```

        它返回第二个参数类型的元素。

    *   ```scala
        abstract def _3: T3
        ```

        它返回第三个参数类型的元素。

    *   ```scala
        abstract def canEqual(that: Any): Boolean
        ```

        如果两个实例相等，则返回 true，否则返回 false。

**示例:**

```scala
// Scala program of a trait
// Product3

// Creating an object
object GfG
{

    // Main method
    def main(args: Array[String]) 
    {

        // Applying Produt3 trait
        // and assigning values
        val x: Product3[String, Int, Double] =
        {
            ("GeeksforGeeks", 32, 43)
        }
        // Displays the first element
        println(x._1)

        // Displays the second element
        println(x._2)

        // Displays the third element
        println(x._3)

    }
}
```

**Output:**

```scala
GeeksforGeeks
32
43.0

```