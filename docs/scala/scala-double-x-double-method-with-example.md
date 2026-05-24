# 斯卡拉双人！=(x: Double)方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-double-x-double-method-with-example/](https://www.geeksforgeeks.org/scala-double-x-double-method-with-example/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。**！=(x: Double)** 方法用于检查给定的 Double 值是否相等。

> **方法定义–**def！=(x: Double):布尔值
> 
> **返回–**如果该值不等于 x，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program to explain working 
// of Double !=(x: Double) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Double) function
        val result = (10.1234500).toLong.!=(10:Double)

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
// Scala program to explain working
// of Long !=(x: Double) function

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Double) function
        val result = 11.86000000.toLong.!= (1296000:Double)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```