# Scala 迭代器 mkString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-MK string-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-mkstring-method-with-example/)

**mkString()** 方法属于抽象迭代器类的具体值成员。它用于在字符串中显示集合的所有元素。
**方法定义:**

```scala
val result = iter.mkString

```

这里，我们在*结果*变量中存储字符串。
**返回类型:**
返回指定集合的字符串表示形式。
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

        // Creating an Iterator 
        val iter = Iterator(3, 6, 15, 19, 21)

        // Applying mkString method
        val result = iter.mkString

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
36151921

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

        // Creating an Iterator 
        val iter = Iterator(0, 0, 1)

        // Applying mkString method
        val result = iter.mkString

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
001

```