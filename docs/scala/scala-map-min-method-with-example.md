# Scala Map min()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-min-method-with-example/](https://www.geeksforgeeks.org/scala-map-min-method-with-example/)

利用 **min()** 方法寻找地图的最小元素。

> **方法定义:** def min: (A，B)
> 
> **返回类型:**返回地图的最小元素。

**示例#1:**

```scala
// Scala program of min()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2)

        // Applying min method 
        val result = m1.min

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
(cs, 2)

```

正如我们在上面的例子中看到的 **cs** 是地图中最小的元素。
**例 2:**

```scala
// Scala program of min()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3, "for" -> 6)

        // Applying min method 
        val result = m1.min

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
(for, 6)

```