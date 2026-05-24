# Scala String equals()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-equals-method-with-example/](https://www.geeksforgeeks.org/scala-string-equals-method-with-example/)

利用**等于()**方法检查所述字符串和对象是否相等。

> **方法定义:**布尔等于(Object anObject)
> **返回类型:**如果字符串与所述对象相同，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of equals()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating an array
        val m1 = Array('N', 'i', 'd', 'h', 'i')

        // Applying equals() method
        val result = "Nidhi".equals("Nidhi")

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
// Scala program of equals()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {
        // Creating an array
        val m1 = Array('N', 'i', 'd', 'h', 'i')

        // Applying equals() method
        val result = "Nidhi".equals("Nidh")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```