# Scala List size()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-size-method-with-example/](https://www.geeksforgeeks.org/scala-list-size-method-with-example/)

利用 **size()** 方法找到所述列表中的元素数量。

> **方法定义:** def size(): Int
> 
> **返回类型:**返回指定列表中的元素数量。

**示例#1:**

```scala
// Scala program of size()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3, 4, 5)

        // Applying size method
        val result = m1.size

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
5

```

**例 2:**

```scala
// Scala program of size()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 0)

        // Applying size method
        val result = m1.size

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
2

```