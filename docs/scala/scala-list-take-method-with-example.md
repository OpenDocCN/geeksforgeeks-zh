# Scala List 带示例的 take()方法

> 原文:[https://www . geesforgeks . org/Scala-list-take-method-with-example/](https://www.geeksforgeeks.org/scala-list-take-method-with-example/)

**take()** 方法属于类*列表*的值成员。它用于从列表中获取第一个 *n* 元素。

> **方法定义:** deftake(n: Int):列表[A]
> 
> 其中， *n* 是要从列表中获取的元素数量。
> 
> **返回类型:**它返回一个列表，该列表只包含所述列表中的第一个 *n* 元素，或者如果 *n* 大于给定列表中的元素数量，则返回整个列表。

**示例#1:**

```scala
// Scala program of take()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a List 
        val list = List(1, 2, 3, 4, 5, 6, 7)

        // Applying take method 
        val result = list.take(4)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List(1, 2, 3, 4)

```

**例 2:**

```scala
// Scala program of take()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a List 
        val list = List("a", "b", "c", "d", "e", "f")

        // Applying take method 
        val result = list.take(4)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List(a, b, c, d)

```