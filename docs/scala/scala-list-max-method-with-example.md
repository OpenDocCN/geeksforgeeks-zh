# Scala List max()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-max-method-with-example/](https://www.geeksforgeeks.org/scala-list-max-method-with-example/)

利用 **max()** 方法寻找所述列表中所有元素中最大的元素。

> **方法定义:**def max【B】T2:A】(隐含顺序:数学。订购[乙]):甲
> 
> **返回类型:**返回指定列表中最大的元素。

**示例#1:**

```scala
// Scala program of max()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3)

        // Applying max method
        val result = m1.max

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
// Scala program of max()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(5, 12, 3, 13)

        // Applying max method
        val result = m1.max

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
13

```