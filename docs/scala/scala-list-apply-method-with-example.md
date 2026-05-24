# Scala List 应用()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-apply-method-with-example/](https://www.geeksforgeeks.org/scala-list-apply-method-with-example/)

**apply()** 方法用于通过索引选择列表中的元素。

> **方法定义:**定义应用(n: Int): A
> 
> **返回类型:**它通过其索引从给定列表中返回一个元素，该索引作为参数出现在 apply 方法中。

**示例#1:**

```scala
// Scala program of apply()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 3, 5, 2)

        // Applying apply method
        val res = m1.apply(3)

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
2

```

**例 2:**

```scala
// Scala program of apply()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 3, 5, 2)

        // Applying apply method
        val res = m1.apply(0)

        // Displays output
        println(res)

    }
}
```

**Output:**

```scala
1

```