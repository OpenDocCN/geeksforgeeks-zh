# Scala Int %(x: Byte)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-byte-method-with-example-4/](https://www.geeksforgeeks.org/scala-int-x-byte-method-with-example-4/)

当指定的 int 值除以 Byte 值时，使用 **%(x: Byte)** 方法返回余数。

> **方法定义:** (Int_Value)。%(Byte_Value)
> **返回类型:**当指定的 int 值除以 Byte 值时返回余数。

**示例#1:**

## 斯卡拉

```scala
// Scala program of Int %(x: Byte)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying Int %(x: Byte) function
        val result = (100).%(50)

        // Displays output
        println(result)

    }
}
```

**Output:** 

```scala
0
```

**例 2:**

## 斯卡拉

```scala
// Scala program of Int %(x: Byte)
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying Int %(x: Byte) function
        val result = (100).%(40)

        // Displays output
        println(result)

    }
}
```

**Output:** 

```scala
20
```