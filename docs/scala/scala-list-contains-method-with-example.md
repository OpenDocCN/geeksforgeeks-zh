# Scala List 包含()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-list-contains-method-with-example/](https://www.geeksforgeeks.org/scala-list-contains-method-with-example/)

**contains()** 方法用于检查列表中是否存在某个元素。

> **方法定义:** def 包含(elem: Any):布尔值
> 
> **返回类型:**如果出现在*中的元素包含*方法作为参数也出现在所述列表中，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of contains()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 3, 5, 2)

        // Applying contains method
        val res = m1.contains(1)

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of contains()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 3, 5, 2)

        // Applying contains method
        val res = m1.contains(7)

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
false

```