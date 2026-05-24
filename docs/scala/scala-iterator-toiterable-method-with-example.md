# Scala 迭代器 to Chantee()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-to imiterate-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-toiterable-method-with-example/)

**to Itanimate()**属于类抽象迭代器的具体值成员。它在类*旅行可通行一次*和*旅行可通行一次*中定义。它将指定的可遍历或迭代器转换为可迭代集合。无限规模的收藏不会结束。

> **方法定义:**定义为可迭代的:可迭代的【A】
> 
> **返回类型:**返回包含所述可遍历或迭代器的所有元素的可迭代的。

**例:**

```scala
// Scala program of toIterable()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Declaring an iterator
        val iter = Iterator(3, 2, 5, 9)

        // Applying toIterable method
        val result = iter.toIterable

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Stream(3, ?)

```