# Scala List addString()方法，有一个开始、一个分隔符和一个带示例的结尾

> 原文:[https://www . geesforgeks . org/Scala-list-addstring-method-with-start-a-separator-and-end-with-example/](https://www.geeksforgeeks.org/scala-list-addstring-method-with-a-start-a-separator-and-an-end-with-example/)

该方法与 **addString()** 方法相同，但这里还包括一个开始、一个分隔符和一个结束。

> **方法定义:** def addString(b:可变。StringBuilder，开始:String，sep: String，结束:String):可变。StringBuilder
> 
> 其中， *sep* 是所述的分隔符。
> 
> **返回类型:**它返回字符串生成器中列表的元素，这里还包括一个开始、一个分隔符和一个结束。

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

        // Creating a list
        val m1 = List(1, 3, 5, 2)

        // Applying addString method
        val res = m1.addString(new StringBuilder(), "_", "*", "_")

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
_1*3*5*2_

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

        // Creating a list
        val m1 = List(1, 3, 5, 2)

        // Applying addString method
        val res = m1.addString(new StringBuilder(), "(", "/", ")")

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
(1/3/5/2)

```