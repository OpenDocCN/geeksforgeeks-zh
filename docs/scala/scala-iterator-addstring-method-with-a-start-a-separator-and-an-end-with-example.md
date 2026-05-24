# Scala 迭代器 addString()方法，以示例

开头、分隔符和结尾

> 原文:[https://www . geesforgeks . org/Scala-iterator-add string-method-with-start-a-separator-and-end-with-example/](https://www.geeksforgeeks.org/scala-iterator-addstring-method-with-a-start-a-separator-and-an-end-with-example/)

用于将 Scala 迭代器的元素附加到字符串生成器的方法。该方法与 **addString()** 方法相同，但这里还包括一个开始、一个分隔符和一个结束。

> **方法定义:** def addString(b:可变。StringBuilder，开始:String，sep: String，结束:String):可变。StringBuilder
> 
> 其中， *sep* 是所述的分隔符。
> 
> **返回类型:**返回字符串生成器中迭代器的元素，这里还包括一个开始、一个分隔符和一个结束。

**示例#1:**

```scala
// Scala program of addString() method
// with a start, a separator and an
// end

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Iterator
        val m1 = Iterator(1, 3, 4, 8)

        // Applying addString method 
        val result = m1.addString(new StringBuilder(), "=>", "|", ".")

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
=>1|3|4|8.

```

**例 2:**

```scala
// Scala program of addString() method
// with a start, a separator and an
// end

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Iterator
        val m1 = Iterator(1, 3, 3, 8)

        // Applying addString method 
        val result = m1.addString(new StringBuilder(), "=>", "|", ".")

        // Displays output
        println(result)
    }
}
```

**输出:**

```scala
=>1|3|3|8.

```

所以，在这里，相同的元素不会像在地图中那样被移除。