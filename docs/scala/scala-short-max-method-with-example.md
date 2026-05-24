# Scala Short max()方法示例

> 原文:[https://www . geesforgeks . org/Scala-short-max-method-with-example/](https://www.geeksforgeeks.org/scala-short-max-method-with-example/)

利用 **max()** 方法寻找两个指定短类型的最大值。

> **方法定义:** def max(即:短):短
> 
> **返回类型:**返回最大值的 Short 类型数。

**例:1#**

```scala
// Scala program of max()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying max() method 
        val result = (-1000).max(999)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
999

```

**例:2#**

```scala
// Scala program of max()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying max() method
        val result = (990).max(1000)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1000

```