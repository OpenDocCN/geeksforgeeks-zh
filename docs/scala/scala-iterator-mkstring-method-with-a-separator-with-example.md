# 带分隔符的 Scala 迭代器 mkString()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-iterator-MK string-method-with-separator-with-example/](https://www.geeksforgeeks.org/scala-iterator-mkstring-method-with-a-separator-with-example/)

此方法与 **mkString()** 方法相同，但此处包含一个分隔符。

> **方法定义:**def mkString(sep:String):String
> 
> **返回类型:**用给定的分隔符返回指定集合的字符串表示形式。

**示例#1:**

```scala
// Scala program of mkString()
// method with a separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(1, 2, 3, 5)

        // Applying mkString method 
        val result = iter.mkString("*")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
1*2*3*5

```

**例 2:**

```scala
// Scala program of mkString()
// method with a separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(1, 2, 3, 5)

        // Applying mkString method 
        val result = iter.mkString("0")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
1020305

```