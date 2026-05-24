# Scala List addString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-addstring-method-with-example/](https://www.geeksforgeeks.org/scala-list-addstring-method-with-example/)

**addString()** 方法用于将列表的所有元素追加到字符串生成器中。

> **方法定义:**def add string(b:StringBuilder):StringBuilder
> 
> **返回类型:**它将列表的元素返回给字符串生成器。

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
        val res = m1.addString(new StringBuilder())

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
1352

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
        val m1 = List(1, 1, 5, 2)

        // Applying addString method
        val res = m1.addString(new StringBuilder())

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
1152

```