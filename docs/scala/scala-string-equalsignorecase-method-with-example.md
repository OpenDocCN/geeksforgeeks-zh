# Scala String equalsignorase()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-equalsignorace-method-with-example/](https://www.geeksforgeeks.org/scala-string-equalsignorecase-method-with-example/)

通过忽略大小写差异，使用**equalsignorase()**方法检查所述字符串和对象是否相等。

> **方法定义:**Boolean equalsIgnoreCase(String other String)
> **返回类型:**如果字符串与忽略大小写差异的对象相同，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of equalsIgnoreCase()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating an array
        val m1 = Array('N', 'i', 'd', 'h', 'i')

        // Applying equalsIgnoreCase() method
        val result = "Nidhi".equalsIgnoreCase("Nidhi")

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
// Scala program of equalsIgnoreCase()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating an array
        val m1 = Array('N', 'i', 'd', 'h', 'i')

        // Applying equalsIgnoreCase() method
        val result = "Nidhi".equalsIgnoreCase("nidhi")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```