# Scala 迭代器 addString()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-add string-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-addstring-method-with-example/)

**addString()** 方法属于类*抽象迭代器*的具体值成员。它在类*中定义。它用于将 Scala 迭代器的元素附加到字符串生成器中。*

> **方法定义:**def add string(b:StringBuilder):StringBuilder
> 
> **返回类型:**返回添加了元素的字符串生成器。

**示例#1:**

```scala
// Scala program of addString()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(7, 6, 8, 1)

        // Applying addString method 
        val result = iter.addString(new StringBuilder())

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
7681

```

**例 2:**

```scala
// Scala program of addString()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(7.7, 6.1, 8.6, 1.1)

        // Applying addString method 
        val result = iter.addString(new StringBuilder())

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
7.76.18.61.1

```