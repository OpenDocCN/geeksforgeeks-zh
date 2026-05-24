# Scala 字符串 contentEquals()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-content equals-method-with-example/](https://www.geeksforgeeks.org/scala-string-contentequals-method-with-example/)

**contentEquals()** 方法用于将字符串与 **StringBuffer** 的内容进行比较。

> **方法定义:**布尔 contentEquals(StringBuffer sb)
> **返回类型:**如果内容等于所述字符串，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of contentEquals()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a StringBuffer
        val m1=new StringBuffer("Nidhi")

        // Applying contentEquals() method
        val result = "Nidhi".contentEquals(m1)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of contentEquals()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating a StringBuffer
        val m1=new StringBuffer("Nidhi")

        // Applying contentEquals() method
        val result = "nidhi".contentEquals(m1)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```