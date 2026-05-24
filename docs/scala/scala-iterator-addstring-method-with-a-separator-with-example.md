# 带分隔符的 Scala 迭代器 addString()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-iterator-add string-method-with-separator-with-example/](https://www.geeksforgeeks.org/scala-iterator-addstring-method-with-a-separator-with-example/)

这个方法与 **addString()** 方法相同，但是这里我们甚至可以在迭代器的所有元素之间包含一个*分隔符*。

> **方法定义:**def addString(b:StringBuilder，sep: String): StringBuilder
> 其中， *sep* 为分隔符。
> 
> **返回类型:**它返回字符串生成器中迭代器的元素以及指定的分隔符。

**示例#1:**

```scala
// Scala program of addString()
// method along with separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(11, 12, 13, 14)

        // Applying addString method
        // with a separator
        val result = iter.addString(new StringBuilder(), "#")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
11#12#13#14

```

**例 2:**

```scala
// Scala program of addString()
// method along with separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(5, 6, 9)

        // Applying addString method
        // with a separator
        val result = iter.addString(new StringBuilder(), "*")

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
5*6*9

```