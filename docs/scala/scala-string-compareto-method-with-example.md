# Scala 字符串比较()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-compare to-method-with-example/](https://www.geeksforgeeks.org/scala-string-compareto-method-with-example/)

**compareTo()** 方法用于将一个字符串与另一个字符串进行比较。
**需要记住的几点:**

*   这里，如果一个字符串(S1)和字符串(S2)在比较中相同，那么这个方法返回零。
*   如果 S1 小于 S2，则返回一个负数，即字符值的差值。
*   如果 S1 大于 S2，则返回正数。

> **方法定义:** int compareTo(String 另一个字符串)
> **返回类型:**返回一个整数。

**示例#1:**

```scala
// Scala program of compareTo()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a String
        val m1 = "Nidhi"

        // Applying compareTo() method
        val result = m1.compareTo("Nidhi")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
0

```

它返回零，因为两个字符串是相同的。
**例 2:**

```scala
// Scala program of compareTo()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a String
        val m1 = "Nidhi"

        // Applying compareTo() method
        val result = m1.compareTo("Nidh")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
1

```

它返回一个正数，因为这里的 S1 比 S2 大。
**例 3:**

```scala
// Scala program of compareTo()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a String
        val m1 = "Nidhi"

        // Applying compareTo() method
        val result = m1.compareTo("nidh")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-32

```

它返回一个负数，因为这里的 S1 比 S2 小。