# Scala Map isEmpty()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-isempty-method-with-example/](https://www.geeksforgeeks.org/scala-map-isempty-method-with-example/)

**isEmpty()** 方法用于检查给定地图是否为空。

> **方法定义:**定义为空:布尔值
> 
> **返回类型:**如果所述地图为空，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of isEmpty()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map(3 -> "geeks", 1 -> "for", 2 -> "cs", 3 -> "geeks")

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

        // Creating map
        val m1 = Map()

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