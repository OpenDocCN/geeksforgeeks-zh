# 斯卡拉飘！=(x: Char)方法示例

> 原文:[https://www . geesforgeks . org/Scala-float-x-char-method-with-example-9/](https://www.geeksforgeeks.org/scala-float-x-char-method-with-example-9/)

**！=(x: Char)** 方法用于检查给定的 Float 和 Char 值是否相等。

> **方法定义:** (Float_Value)！=(x: Char)
> **返回类型:**如果给定的 Float 和 Char 值不相等，则返回 true，否则返回 false。

**示例#1:**

## 斯卡拉

```scala
// Scala program of Float !=(x: Char)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Char) function
        val result = (65.0).!=('A')

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

## 斯卡拉

```scala
// Scala program of Float !=(x: Char)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying !=(x: Char) function
        val result = (65.0).!=('C')

        // Displays output
        println(result)

    }
}
```

**Output:** 

```scala
true
```