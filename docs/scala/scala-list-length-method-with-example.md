# Scala List length()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-length-method-with-example/](https://www.geeksforgeeks.org/scala-list-length-method-with-example/)

利用**长度()**方法求列表的长度。

> **方法定义:**定义长度:整数
> 
> **返回类型:**返回所述列表的长度。

**例:1#**

```scala
// Scala program of length()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(3, 4, 5, 7, 8)

        // Applying length method
        val result = m1.length

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
5

```

**例:2#**

```scala
// Scala program of length()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List()

        // Applying length method
        val result = m1.length

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```