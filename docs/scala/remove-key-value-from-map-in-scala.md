# 从 Scala 的地图中移除键值

> 原文:[https://www . geesforgeks . org/remove-key-value-from-map-in-Scala/](https://www.geeksforgeeks.org/remove-key-value-from-map-in-scala/)

Scala 映射键的删除可以通过**–**运算符获得。该操作符用于删除地图的键集。
**语法:**

```scala
def -(elem1: A, elem2: A, elems: A*): Map[A, B]

```

它返回一个包含给定地图的所有元素的新地图，除了使用上述运算符删除的一组关键字。
**例 1:**

```scala
// Scala program of deleting 
// keys

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3) 

        // Applying - operator
        val result = m1.-("for")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(geeks -> 5)

```

在上例中，删除了键的**。
**例 2:****

```scala
// Scala program of deleting 
// keys

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2) 

        // Applying - operator
        val result = m1.-("for", "geeks")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(cs -> 2)

```