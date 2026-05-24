# Scala Int compareTo()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-compare to-method-with-example/](https://www.geeksforgeeks.org/scala-int-compareto-method-with-example/)

如果第一个整数值等于第二个整数值，则使用 **compareTo()** 方法返回 0，如果第一个大于第二个，则返回 1，如果第一个小于第二个，则返回-1。

> **方法定义:** (First_Integer_Value)。compare to(Second _ Integer _ Value)
> **返回类型:**如果第一个整数值等于第二个整数值，则返回 0；如果第一个大于第二个，则返回 1；如果第一个小于第二个，则返回-1。

**示例#1:**

## 斯卡拉

```scala
// Scala program of Int compareTo()
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating first Int number
        val m1 = 3

        // Applying compareTo method
        val result = m1.compareTo(3)

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

## 斯卡拉

```scala
// Scala program of Int compareTo()
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating first Int number
        val m1 = 3

        // Applying compareTo method
        val result = m1.compareTo(2)

        // Displays output
        println(result)

    }
}
```

**Output:** 

```scala
1
```

**例 3:**

## 斯卡拉

```scala
// Scala program of Int compareTo()
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating first Int number
        val m1 = 3

        // Applying compareTo method
        val result = m1.compareTo(9)

        // Displays output
        println(result)

    }
}
```

**Output:** 

```scala
-1
```