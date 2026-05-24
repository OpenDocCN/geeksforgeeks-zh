# Scala Int & (x: Long)方法示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-long-method-with-example-3/](https://www.geeksforgeeks.org/scala-int-x-long-method-with-example-3/)

**& (x: Long)** 方法用于返回长值对指定 int 值进行按位 AND 运算的结果。

> **方法定义:** (Int_Value)。&(长 _ 值)
> 
> **返回类型:**通过长值返回指定 int 值的按位 AND 运算结果。

**示例#1:**

```scala
// Scala program of Int &(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int &(x: Long) function
        val result = (10).&(6)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
2

```

**例 2:**

```scala
// Scala program of Int &(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int &(x: Long) function
        val result = (10).&(8)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
8

```