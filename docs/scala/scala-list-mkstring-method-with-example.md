# Scala List mkString()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-MK string-method-with-example/](https://www.geeksforgeeks.org/scala-list-mkstring-method-with-example/)

**mkString()** 方法用于显示字符串中列表的所有元素。

> **方法定义:** def mkString: String
> 
> **返回类型:**它以字符串形式返回列表的所有元素。

**示例#1:**

```scala
// Scala program of mkString()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(2, 3, 5, 7, 8)

        // Applying mkString method
        val result = m1.mkString

        // Displays output
        println(result)

    }
} 

```

**Output:**

```scala
23578

```

**例 2:**

```scala
// Scala program of mkString()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(2, 3, 5, 7, 5)

        // Applying mkString method
        val result = m1.mkString

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
23575

```