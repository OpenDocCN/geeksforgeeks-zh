# Scala List min()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-min-method-with-example/](https://www.geeksforgeeks.org/scala-list-min-method-with-example/)

利用 **min()** 方法寻找所述列表中所有元素的最小元素。

> **方法定义:**def min【B】T2:A】(隐含顺序:数学。订购[乙]):甲
> 
> **返回类型:**返回指定列表中所有元素中最小的一个。

**示例#1:**

```scala
// Scala program of min()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3)

        // Applying min method
        val result = m1.min

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
1

```

**例 2:**

```scala
// Scala program of min()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(5, 12, 3, 13)

        // Applying min method
        val result = m1.min

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
3

```