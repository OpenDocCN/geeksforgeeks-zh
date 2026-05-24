# Scala 迭代器 forall()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-for all-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-forall-method-with-example/)

forall() 方法属于类*抽象迭代器*的具体值成员。它在类*中定义。它测试所使用的谓词是否适用于所述集合的所有元素。对于无限大小的集合，它可能不会终止。*

> **方法定义:**定义为 all(p: (A) = >布尔型:布尔型
> 
> **返回类型:**如果指定的集合为空，或者给定的谓词 p 适用于该集合的所有元素，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of forall()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(3, 6, 15, 12, 21)

        // Applying forall method
        val result= iter.forall(x => {x % 3 == 0})

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
// Scala program of forall()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(3, 6, 15, 19, 21)

        // Applying forall method
        val result= iter.forall(x => {x % 3 == 0})

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
false

```