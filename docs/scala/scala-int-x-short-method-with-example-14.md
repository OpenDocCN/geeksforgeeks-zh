# Scala Int>>>(x:Short)法同例

> 原文:[https://www . geesforgeks . org/Scala-int-x-short-method-with-example-14/](https://www.geeksforgeeks.org/scala-int-x-short-method-with-example-14/)

**> > > (x: Short)** 方法用于返回一个值，该值是 int 值右移指定短值的结果。这里左边的位用零填充。

> **方法定义:** (Int_Value)。>>>(Short _ Value)
> **返回类型:**返回一个值，该值是 int 值右移指定短值的结果。

**示例#1:**

```scala
// Scala program of Int >>>(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>>(x: Short) function
        val result = (15).>>>(2)

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
// Scala program of Int >>>(x: Short)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>>(x: Short) function
        val result = (15).>>>(3)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1

```