# Scala Int > > > (x: Long)法同例

> 原文:[https://www . geesforgeks . org/Scala-int-x-long-method-with-example-14/](https://www.geeksforgeeks.org/scala-int-x-long-method-with-example-14/)

**> > > (x: Long)** 方法用于返回一个值，该值是 int 值右位移位指定的 Long 值的结果。这里左边的位用零填充。

> **方法定义:** (Int_Value)。> > > (Long_Value)
> **返回类型:**返回一个值，该值是 int 值右移指定长值的结果。

**示例#1:**

```scala
// Scala program of Int >>>(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>>(x: long) function
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
// Scala program of Int >>>(x: Long)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >>>(x: Long) function
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