# Scala Int & (x: Short)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-short-method-with-example-3/](https://www.geeksforgeeks.org/scala-int-x-short-method-with-example-3/)

**& (x: Short)** 方法用于返回短值对指定 int 值进行按位 AND 运算的结果。

> **方法定义:** (Int_Value)。&(短 _ 值)
> 
> **返回类型:**通过短值返回指定 int 值的按位 AND 运算结果。

**示例#1:**

```scala
// Scala program of Int &(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int &(x: short) function
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
// Scala program of Int &(x: short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int &(x: short) function
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