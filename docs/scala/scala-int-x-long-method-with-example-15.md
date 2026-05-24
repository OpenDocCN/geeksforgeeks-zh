# Scala Int ^(x:长)方法示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-long-method-with-example-15/](https://www.geeksforgeeks.org/scala-int-x-long-method-with-example-15/)

**^(x:长)**方法用于返回一个值，该值是 int 和指定长值的按位异或运算的结果。

> **方法定义:** (Int_Value)。^(Long_Value)
> **返回类型:**它返回一个值，该值是 int 和指定 Long 值按位异或运算的结果。

**示例#1:**

```scala
// Scala program of Int ^(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int ^(x: Long) function
        val result = (15).^(2)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
13

```

**例 2:**

```scala
// Scala program of Int ^(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int ^(x: Long) function
        val result = (15).^(3)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
12

```