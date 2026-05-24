# Scala 迭代器 toSeq()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-toseq-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-toseq-method-with-example/)

**toSeq()** 方法属于抽象迭代器类的具体值成员。它相当于*序列*方法，但是这个方法更快。

> **方法定义:**val result = ITER . toseq
> 
> **返回类型:**它将所述集合作为序列返回。

**示例#1:**

```scala
// Scala program of toSeq()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Iterator 
        val iter = Iterator(2, 5, 7, 8, 9)

        // Applying toSeq method 
        val result = iter.toSeq

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Stream(2, ?)

```