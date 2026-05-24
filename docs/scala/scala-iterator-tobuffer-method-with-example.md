# Scala 迭代器 toBuffer()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-to buffer-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-tobuffer-method-with-example/)

**toBuffer()** 方法属于类抽象迭代器的具体值成员。它在类*旅行可通行一次*和*旅行可通行一次*中定义。它使用所述*可遍历*或*迭代器*的内容来产生新的可变缓冲区。无限规模的收藏不会结束。

> **方法定义:**def to Buffer:Buffer【B】
> 
> **返回类型:**它从所述迭代器的元素中返回一个缓冲区。

**例:**

```scala
// Scala program of toBuffer()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(3, 2, 5, 9)

        // Applying toBuffer method
        val result = iter.toBuffer

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
ArrayBuffer(3, 2, 5, 9)

```