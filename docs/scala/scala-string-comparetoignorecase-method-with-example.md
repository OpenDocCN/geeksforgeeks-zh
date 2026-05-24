# Scala String comparetionignorecase()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-compare toignorecase-method-with-example/](https://www.geeksforgeeks.org/scala-string-comparetoignorecase-method-with-example/)

像*比较*方法一样，使用 **compareToIgnoreCase()** 方法来比较两个字符串，但是这里在比较时忽略大小写差异。

> **方法定义:**int compareToIgnoreCase(String str)
> **返回类型:**与 *compareTo()* 方法相同，但这里只忽略大小写差异。

**例:1#**

```scala
// Scala program of compareToIgnoreCase()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a String
        val m1 = "Nidhi"

        // Applying compareToIgnoreCase() method
        val result = m1.compareToIgnoreCase("Nidhi")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```

**例 2:**

```scala
// Scala program of compareToIgnoreCase()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a String
        val m1 = "Nidhi"

        // Applying compareToIgnoreCase() method
        val result = m1.compareToIgnoreCase("NiDhi")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```

这里，即使有大小写差异，两个字符串也被认为是相同的。
**例 3:**

```scala
// Scala program of compareToIgnoreCase()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a String
        val m1 = "Nidhi"

        // Applying compareToIgnoreCase() method
        val result = m1.compareToIgnoreCase("NiDh")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1

```