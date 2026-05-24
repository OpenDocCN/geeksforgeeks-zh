# Scala 迭代器 length()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-length-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-length-method-with-example/)

**length()** 方法属于类*抽象迭代器*的具体值成员。它在类*迭代器*中定义。它也与方法*大小*相同，也用于查找所述集合的长度。

> **方法定义:**最终定义长度:Int
> 
> **返回类型:**返回所述集合的长度。

**示例#1:**

```scala
// Scala program of length()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(2, 3, 5, 7, 11)

        // Applying length method
        val iter1 = iter.length

        // Displays output
        println(iter1)

    }
}
```

**输出:**

```scala
5

```