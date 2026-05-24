# Scala 迭代器 mkString()方法，带有一个开始、一个分隔符和一个带示例的结尾

> 原文:[https://www . geesforgeks . org/Scala-iterator-MK string-method-with-start-a-separator-and-end-with-example/](https://www.geeksforgeeks.org/scala-iterator-mkstring-method-with-a-start-a-separator-and-an-end-with-example/)

该方法也与 **mkString()** 方法相同，但在这里它伴随着一个开始、一个分隔符和一个结束。

> **方法定义:** def mkString(开始:String，sep: String，结束:String): String
> 
> 其中，*开始*为起始弦，*九月*为分离弦，*结束*为结束弦。
> 
> **返回类型:**返回指定集合的字符串表示形式，以及开始、分隔符和结束。

**示例#1:**

```scala
// Scala program of mkString()
// method with a start, end 
// and a separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(1, 2, 3, 5)

        // Applying mkString method 
        val result = iter.mkString("*", "0", "*")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
*1020305*

```

其中，开始是 ***** ，9 月是 **0** ，结束也是 ***** 。
**例 2:**

```scala
// Scala program of mkString()
// method with a start, end 
// and a separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(1, 2, 3, 5)

        // Applying mkString method 
        val result = iter.mkString("#", "*", "#")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
#1*2*3*5#

```