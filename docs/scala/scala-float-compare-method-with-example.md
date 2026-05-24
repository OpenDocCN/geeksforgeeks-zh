# Scala 浮点比较()方法与示例

> 原文:[https://www . geeksforgeeks . org/Scala-float-compare-method-with-example/](https://www.geeksforgeeks.org/scala-float-compare-method-with-example/)

如果第一个数字等于第二个数字，则使用 **compare()** 方法返回 0，如果第一个数字大于第二个数字，则返回 1，如果第一个数字小于第二个数字，则返回-1。

> **方法定义:** (First_Number)。compare(Second _ Number)
> 
> **返回类型:**如果第一个数字等于第二个数字，则返回 0，如果第一个数字大于第二个数字，则返回 1，如果第一个数字小于第二个数字，则返回-1。

**示例#1:**

```scala
// Scala program of Float compare()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying compare method
        val result = (5).compare(5)

        // Displays output
        println(result)

    }
} 
```

**输出:**

```scala
0

```