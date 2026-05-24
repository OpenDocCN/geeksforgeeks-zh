# Scala Int signum()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-signum-method-with-example/](https://www.geeksforgeeks.org/scala-int-signum-method-with-example/)

**signum()** 方法用于返回 1 表示正指定数，-1 表示负指定数，0 表示 0 指定值。

> **方法定义:**(值)。正负号函数
> 
> **返回类型:**对于正的指定数返回 1，对于负的指定数返回-1，对于 0 的指定值返回 0。

**示例#1:**

```scala
// Scala program of Int signum()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying signum method
        val result = (5).signum

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
// Scala program of Int signum()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying signum method
        val result = (-5).signum

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
-1

```