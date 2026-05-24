# Scala Float compareTo()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-compare to-method-with-example/](https://www.geeksforgeeks.org/scala-float-compareto-method-with-example/)

如果第一个数字等于第二个数字，则使用 **compareTo()** 方法返回 0，如果第一个数字大于第二个数字，则返回 1，如果第一个数字小于第二个数字，则返回-1。

> **方法定义:** (First_Number)。compare to(Second _ Number)
> 
> **返回类型:**如果第一个数字等于第二个数字，则返回 0，如果第一个数字大于第二个数字，则返回 1，如果第一个数字小于第二个数字，则返回-1。

**示例#1:**

```scala
// Scala program of Float compareTo()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating first float number 
        val m1 = 3.4

        // Applying compareTo method
        val result = m1.compareTo(3.4)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
0

```