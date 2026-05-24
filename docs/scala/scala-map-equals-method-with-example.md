# Scala Map equals()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-equals-method-with-example/](https://www.geeksforgeeks.org/scala-map-equals-method-with-example/)

**等于()**方法用于检查两个映射是否具有相同的键值对。

> **方法定义:** def 等于(即:任意):布尔值
> 
> **返回类型:**如果两个映射的键值对相同，则返回真，否则返回假。

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

        // Creating maps
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs"-> 2)
        val m2 = Map("cs" -> 2, "for" -> 3, "geeks"-> 5)

        // Applying equals method
        val result = m1.equals(m2)

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

        // Creating maps
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs"-> 2)
        val m2 = Map("cs" -> 2, "fo" -> 2, "geeks"-> 5)

        // Applying equals method
        val result = m1.equals(m2)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
false

```