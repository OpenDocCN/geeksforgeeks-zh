# Scala Int > > (x: Byte)方法示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-byte-method-with-example-13/](https://www.geeksforgeeks.org/scala-int-x-byte-method-with-example-13/)

**> > (x: Byte)** 方法用于返回一个值，该值是 int 值右移指定字节值的结果。

> **方法定义:** (Int_Value)。> >(字节值)
> **返回类型:**返回一个值，该值是 int 值右移指定字节值的结果。

**示例#1:**

```scala
// Scala program of Int >>(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>(x: Byte) function
        val result = (15).>>(2)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
3

```

**例 2:**

```scala
// Scala program of Int >>(x: Byte)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>(x: Byte) function
        val result = (15).>>(3)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1

```