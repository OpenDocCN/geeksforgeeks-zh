# Scala Int compare()方法与示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-compare-method-with-example/](https://www.geeksforgeeks.org/scala-int-compare-method-with-example/)

如果第一个整数值等于第二个整数值，则使用 **compare()** 方法返回 0，如果第一个大于第二个，则返回 1，如果第一个小于第二个，则返回-1。

> **方法定义:** (First_Integer_Value)。compare(Second _ Integer _ Value)
> **返回类型:**如果第一个整数值等于第二个整数值，则返回 0，如果第一个大于第二个，则返回 1，如果第一个小于第二个，则返回-1。

**示例#1:**

```scala
// Scala program of Int compare()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying compare method
        val result = (10).compare(10)

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
// Scala program of Int compare()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying compare method
        val result = (10).compare(5)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1

```

**示例#3:**

```scala
// Scala program of Int compare()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying compare method
        val result = (10).compare(20)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-1

```