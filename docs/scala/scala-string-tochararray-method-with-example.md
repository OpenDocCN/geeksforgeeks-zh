# Scala String toCharArray()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-to chararray-method-with-example/](https://www.geeksforgeeks.org/scala-string-tochararray-method-with-example/)

利用 **toCharArray()** 方法将指定的字符串转换为 *CharArray* 。

> **方法定义:** char[] toCharArray()
> 
> **返回类型:**返回 CharArray。

**例:1#**

```scala
// Scala program of toCharArray()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toCharArray method
        val result = "GeeksforGeeks".toCharArray()

        for(m1<-result)
        {
            // Displays output
            println(m1)
        }

    }
} 
```

**Output:**

```scala
G
e
e
k
s
f
o
r
G
e
e
k
s

```

**例:2#**

```scala
// Scala program of toCharArray()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying toCharArray method
        val result = "Nidhi".toCharArray()

        for(m1 <- result)
        {
            // Displays output
            println(m1)
        }

    }
} 
```

**Output:**

```scala
N
i
d
h
i

```