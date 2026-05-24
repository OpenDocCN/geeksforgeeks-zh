# Scala List distinct()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-distinct-method-with-example/](https://www.geeksforgeeks.org/scala-list-distinct-method-with-example/)

使用 **distinct()** 方法从所述列表中删除重复元素。

> **方法定义:**定义不同:列表[A]
> 
> **返回类型:**返回一个没有重复的新的元素列表。

**示例#1:**

```scala
// Scala program of distinct()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 1, 3, 3, 5, 2)

        // Applying distinct method
        val res = m1.distinct

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(1, 3, 5, 2)

```

**例 2:**

```scala
// Scala program of distinct()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 1, 3, 3, 3, 5, 4, 5, 2)

        // Applying distinct method
        val res = m1.distinct

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
List(1, 3, 5, 4, 2)

```