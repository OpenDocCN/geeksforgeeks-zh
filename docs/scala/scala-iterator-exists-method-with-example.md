# Scala 迭代器存在()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-exists-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-exists-method-with-example/)

**exists()** 方法属于类*抽象迭代器*的具体值成员。它在类*中定义。它测试所使用的谓词是否适用于所述集合的至少一个元素。对于无限大小的集合，它不会终止。*

> **方法定义:** def 存在(p: (A) = >布尔型:布尔型
> 
> 其中， *p* 为谓语。
> 
> **返回类型:**如果给定的谓词 p 被所述集合的至少一个元素满足，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of exists()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(7, 3, 4, 11, 13)

        // Applying exists method
        val result = iter.exists(x => {x % 2 == 0})

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
// Scala program of exists()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(7, 3, 5, 11, 13)

        // Applying exists method
        val result = iter.exists(x => {x % 2 == 0})

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
false

```