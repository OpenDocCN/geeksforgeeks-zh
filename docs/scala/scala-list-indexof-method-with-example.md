# Scala List indexOf()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-indexof-method-with-example/](https://www.geeksforgeeks.org/scala-list-indexof-method-with-example/)

**indexOf()** 方法用于从该方法中作为参数出现的所述列表中检查元素的索引。

> **方法定义:**定义(elem: A，from: Int): Int 的索引
> 
> **返回类型:**返回参数中存在的元素的索引。

**示例#1:**

```scala
// Scala program of indexOf()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(3, 6, 2, 9, 21)

        // Applying indexOf method
        val result = m1.indexOf(9)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
3

```

**例 2:**

```scala
// Scala program of indexOf()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a list
        val m1 = List(3, 6, 2, 9, 21)

        // Applying indexOf method
        val result = m1.indexOf(3)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```