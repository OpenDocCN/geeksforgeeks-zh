# Scala Map init()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-init-method-with-example/](https://www.geeksforgeeks.org/scala-map-init-method-with-example/)

使用 **init()** 方法删除地图的最后一个元素。它将返回除最后一个元素之外的所有地图元素。

> **方法定义:**定义初始化:映射[A，B]
> 
> **返回类型:**返回地图除最后一个元素外的所有元素。

**示例#1:**

```scala
// Scala program of init()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs"-> 2)

        // Applying init method
        val result = m1.init

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(geeks -> 5, for -> 3)

```

**例 2:**

```scala
// Scala program of init()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5)

        // Applying init method
        val result = m1.init

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map()

```