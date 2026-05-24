# 带分隔符的 Scala List addString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-addstring-method-with-a-separator-with-example/](https://www.geeksforgeeks.org/scala-list-addstring-method-with-a-separator-with-example/)

该方法与 **addString()** 方法相同，但这里还包括一个分隔符。

> **方法定义:**def add String(b:StringBuilder，sep: String): StringBuilder
> 
> **返回类型:**它将列表的元素连同它们之间的分隔符一起返回给字符串生成器。

**示例#1:**

```scala
// Scala program of addString()
// method with a separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 3, 5, 2)

        // Applying addString method
        val res = m1.addString(new StringBuilder(), "*")

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
1*3*5*2

```

**例 2:**

```scala
// Scala program of addString()
// method with a separator

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 3, 5, 2)

        // Applying addString method
        val res = m1.addString(new StringBuilder(), "_")

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
1_3_5_2

```