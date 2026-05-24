# 带示例的标量积分比较方法

> 原文:[https://www . geeksforgeeks . org/Scala-int-compare-method-with-examples/](https://www.geeksforgeeks.org/scala-int-compare-method-with-examples/)

**compare** 是 Scala 中一个 int 类方法，用于将其与操作数进行比较。

> **语法:**(给定 _ 值 1)。比较(给定 _ 值 2)
> 
> **返回:**当给定值 1 小于给定值 2 时，返回-1。当两个值相等时，返回 0。当给定值 1 大于给定值 2 时，返回 1。

**例 1:**

```scala
// Scala Program to demonstrate the 
// compare method of Int class

object GfG
{ 

    // Main Method
    def main(args:Array[String])
    {

        // Applying the method
        val v1 = (451).compare(145)

        // Displaying the output
        println(v1)

    }
} 
```

**Output:**

```scala
1

```

**例 2:**

```scala
// Scala Program to demonstrate the 
// compare method of Int class

object GfG
{ 

    // Main Method
    def main(args:Array[String])
    {

        // Applying the method
        val v1 = (121).compare(1478)

        // Displaying the output
        println(v1)

    }
} 
```

**Output:**

```scala
-1

```