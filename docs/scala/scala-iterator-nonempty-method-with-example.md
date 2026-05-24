# Scala 迭代器非空()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-iterator-non empty-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-nonempty-method-with-example/)

**非空**方法属于抽象迭代器类的具体值成员。它用于检查所述集合是否为空。

> **方法定义:**定义非空:布尔值
> 
> **返回类型:**如果所述集合包含至少一个元素，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of nonEmpty()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(3, 4, 6)

        // Applying nonEmpty method 
        val result = iter.nonEmpty

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
// Scala program of nonEmpty()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an empty Iterator 
        val iter = Iterator()

        // Applying nonEmpty method 
        val result = iter.nonEmpty

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
false

```