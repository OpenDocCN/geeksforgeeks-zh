# 如何从 Scala 图中获取所有值

> 原文:[https://www . geeksforgeeks . org/如何从 scala-map/](https://www.geeksforgeeks.org/how-to-get-all-the-values-from-a-scala-map/) 获取所有值

为了从 Scala 映射中获取所有值，我们需要使用 *values* 方法(以 Iterable 的形式获取所有值)，如果我们想要以迭代器的形式获取值，我们需要使用*ValueSiteror*方法。现在，让我们来看看一些例子。
**例 1:**

```scala
// Scala program of values()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying values method
        val result = m1.values

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
MapLike(geeks, for, cs)

```

这里，使用*值*方法。
**例 2:**

```scala
// Scala program of valuesIterator()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying valuesIterator method
        val result = m1.valuesIterator

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
non-empty iterator

```

这里，使用 *valuesIterator* 方法。