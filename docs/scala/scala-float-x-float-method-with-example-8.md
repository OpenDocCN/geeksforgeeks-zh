# 斯卡拉飘！=(x: Float)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-float-method-with-example-8/](https://www.geeksforgeeks.org/scala-float-x-float-method-with-example-8/)

**！=(x: float)** 方法用于检查给定的第一 Float 和第二 Float 值是否彼此相等。

> **方法定义:** (Float_Value)！=(x:浮动)
> 
> **返回类型:**如果给定的第一个浮点值和第二个浮点值不相等，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Float !=(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Float) function
        val result = (12.4).!=(12.4)

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
// Scala program of Float !=(x: Float)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Float) function
        val result = (12.4).!=(92.4)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```