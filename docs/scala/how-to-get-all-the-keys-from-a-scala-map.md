# 如何从 Scala 地图中获取所有的键

> 原文:[https://www . geeksforgeeks . org/如何从 scala-map/](https://www.geeksforgeeks.org/how-to-get-all-the-keys-from-a-scala-map/) 获取所有密钥

为了从 Scala 映射中获得所有的键，我们需要使用*键集*方法(将所有的键作为一个集合获得)，或者我们可以使用*键*方法，如果您想要获得作为迭代器的键，您需要使用*键迭代器*方法。现在，让我们来看看一些例子。
**示例#1:**

```scala
// Scala program of keySet()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying keySet method
        val result = m1.keySet

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Set(3, 4, 2)

```

这里，使用*键集*方法。
**例 2:**

```scala
// Scala program of keys()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying keys method
        val result = m1.keys

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Set(3, 4, 2)

```

这里，使用*键*方法。
**例 3:**

```scala
// Scala program of keysIterator()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying keysIterator method
        val result = m1.keysIterator

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
non-empty iterator

```

这里，使用*键迭代器*方法。