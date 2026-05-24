# Scala 迭代器 toString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-tostring-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-tostring-method-with-example/)

**toString()** 方法属于抽象迭代器类的具体值成员。它用于将所述迭代器转换为字符串。

> **方法定义:**def toString():String
> 
> **返回类型:**从指定的迭代器返回一个字符串。

**示例#1:**

```scala
// Scala program of toString()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Iterator 
        val iter = Iterator(2, 1, 10)

        // Applying toString method 
        val result = iter.toString

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
non-empty iterator

```