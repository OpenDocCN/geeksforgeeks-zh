# Scala Int > > > (x: Int)法同例

> 原文:[https://www . geesforgeks . org/Scala-int-x-int-method-with-example-14/](https://www.geeksforgeeks.org/scala-int-x-int-method-with-example-14/)

**> > > (x: int)** 方法用于返回一个值，该值是 Int 值右移指定 Int 值的结果。这里左边的位用零填充。

> **方法定义:** (Int_Value)。> > > (int_Value)
> **返回类型:**返回一个值，该值是 Int 值右移指定 Int 值的结果。

**示例#1:**

```scala
// Scala program of Int >>>(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>>(x: Int) function
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
// Scala program of Int >>>(x: Int)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>>(x: Int) function
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