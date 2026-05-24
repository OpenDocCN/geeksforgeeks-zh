# Scala 列表是空操作，示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-isempty-operation-with-example/](https://www.geeksforgeeks.org/scala-list-isempty-operation-with-example/)

**isEmpty** 操作用于检查所述列表是否为空。
**语法:**

```scala
m1.isEmpty
```

这里，m1 是地图名称。isEmpty 是一种方法，如果指定的列表为空，则返回 true，否则返回 false。
**例 1:**

```scala
// Scala program of isEmpty()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(6, 8, 9, 12)

        // Applying isEmpty method
        val result = m1.isEmpty

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
false

```

**例 2:**

```scala
// Scala program of isEmpty()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List()

        // Applying isEmpty method
        val result = m1.isEmpty

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
true

```