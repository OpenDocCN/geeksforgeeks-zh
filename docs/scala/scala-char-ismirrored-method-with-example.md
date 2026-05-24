# Scala Char isMirrored()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-char-is mirrored-method-with-example/](https://www.geeksforgeeks.org/scala-char-ismirrored-method-with-example/)

**isMirrored()** 方法用于检查所述字符值是否被镜像。例如:{}、[]、()等。

> **方法定义:** def isMirrored:布尔值
> 
> **返回类型:**如果所述字符被镜像，则返回真，否则返回假。

**例:1#**

```scala
// Scala program of isMirrored()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isMirrored() method 
        val result = ('{').isMirrored

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
true

```

**例:2#**

```scala
// Scala program of isMirrored()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying isMirrored() method
        val result = ('A').isMirrored

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```