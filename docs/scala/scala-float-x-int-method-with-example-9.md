# 斯卡拉飘！=(x: Int)方法示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-int-method-with-example-9/](https://www.geeksforgeeks.org/scala-float-x-int-method-with-example-9/)

**！=(x: Int)** 方法用于检查给定的 Float 和 Int 值是否相等。

> **方法定义:** (Float_Value)！=(x: Int)
> 
> **返回类型:**如果给定的 Float 和 Int 值不相等，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Float !=(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Int) function
        val result = (12.0).!=(12)

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
// Scala program of Float !=(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Int) function
        val result = (12.4).!=(16)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```