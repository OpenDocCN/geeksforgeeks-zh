# 斯卡拉双人！=(x: Float)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-double-x-float-method-with-example/](https://www.geeksforgeeks.org/scala-double-x-float-method-with-example/)

在 Scala 中，double 是一个 64 位的浮点数，相当于 Java 的 Double 原语类型。**！=(x: Float)** 方法用于检查给定的 Double 值和 Float 是否相等。

> **方法定义–**def！=(x: Float):布尔值
> **返回–**如果该值不等于 x，则返回 true，否则返回 false。

**示例#1:**

## 斯卡拉

```scala
// Scala program to explain working
// of Double !=(x: Float) function

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Float) function
        val result = (10.001254).toDouble.!=(10:Float)

        // Displays output
        println(result)

    }
}
```

**Output:** 

```scala
true
```

**例 2:**

## 斯卡拉

```scala
// Scala program to explain working
// of Double !=(x: Float) function

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Float) function
        val result = 11.86000000.toDouble.!= (1296000.5)

        // Displays output
        println(result)

    }
}
```

**Output:** 

```scala
true
```