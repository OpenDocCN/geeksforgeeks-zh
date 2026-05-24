# Scala |在地图上调用的方法| Set-1

> 原文:[https://www . geesforgeks . org/Scala-地图上调用方法-set-1/](https://www.geeksforgeeks.org/scala-methods-to-call-on-a-map-set-1/)

先决条件- [斯卡拉地图](https://www.geeksforgeeks.org/scala-map/)。

在 Scala 中，调用*图*有最重要的方法。Scala 方法是一个类的一部分，它有一个名称、一个签名、一些可选的注释和任何字节码。被解释为某个对象的成员的函数被称为方法，映射方法与集合完全结合，此外，它是由 Scala 的集合类执行的*可遍历*特性的成员(可遍历性解释了许多具体的方法)。

**调用 Scala 映射最主要的方法如下:**

*   **def ++(xs: Map[(A，B)]:Map[A，B]**
    此方法用于*连接*两个或多个 Map。在连接映射中，它将分开相同的键。
    **示例:**

    ```scala
    // Scala program to concatenate two Map

    // Creating Object
    object GFG 
    {
        // Main method
        def main(args: Array[String]) 
        {

            // Creating maps
            val group1 = Map("Nidhi" -> 23, "Rahul" -> 18)
            val group2 = Map("Geeta" -> 22, "Rahul" -> 18)

            // using ++ as a method
            val concatenate = group1.++(group2)

            // Displays concatenated map
            println( "Concatenation is: " + concatenate)
        }
    }
    ```

    **输出:**

```scala
Concatenation is: Map(Nidhi -> 23, Rahul -> 18, Geeta -> 22)

```