# Scala List splitAt()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-splitat-method-with-example/](https://www.geeksforgeeks.org/scala-list-splitat-method-with-example/)

**splitAt()** 方法属于类*列表*的值成员。它用于在指定位置将给定列表拆分成前缀/后缀对。

> **方法定义:** def splitAt(n: Int):(列表[A]，列表[A])
> 
> 其中， *n* 是我们需要拆分的位置。
> 
> **返回类型:**它返回一对由该列表的第一个 *n* 元素和其他元素组成的列表。

**示例#1:**

```scala
// Scala program of splitAt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a List 
        val list = List("a", "b", "c", "d", "e", "f")

        // Applying splitAt method 
        val result = list.splitAt(3)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
(List(a, b, c), List(d, e, f))

```

**例 2:**

```scala
// Scala program of splitAt()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a List 
        val list = List(1, 2, 3, 4, 5, 6, 7)

        // Applying splitAt method 
        val result = list.splitAt(4)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
(List(1, 2, 3, 4), List(5, 6, 7))

```