# 标量内部比较方法与示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-compare to-method-with-examples/](https://www.geeksforgeeks.org/scala-int-compareto-method-with-examples/)

**compareTo** 是 Scala 中的一个 int 类方法，用于将其与操作数进行比较。它类似于比较方法。

> **语法:**(给定 _ 值 1)。比较(给定值 2)
> **返回:**当给定值 1 小于给定值 2 时返回-1。当两个值相等时，返回 0。当给定值 1 大于给定值 2 时，返回 1。

**例 1:**

## 斯卡拉

```scala
// Scala Program to demonstrate the
// compareTo method of Int class

object GfG
{

    // Main Method
    def main(args:Array[String])
    {

        // Applying the method
        val v1 = (500).compareTo(400)

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

## 斯卡拉

```scala
// Scala Program to demonstrate the
// compareTo method of Int class

object GfG
{

    // Main Method
    def main(args:Array[String])
    {

        // Applying the method
        val v1 = (200).compareTo(700)

        // Displaying the output
        println(v1)

    }
}
```

**Output:** 

```scala
-1
```