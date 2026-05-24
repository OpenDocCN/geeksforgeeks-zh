# Scala List exists()方法，示例

> 原文:[https://www . geesforgeks . org/Scala-list-exists-method-with-example/](https://www.geeksforgeeks.org/scala-list-exists-method-with-example/)

**exists()** 方法用于检查给定的谓词是否满足列表的元素。

> **方法定义:** def 存在(p: (A) = >布尔型:布尔型
> 
> **返回类型:**如果所述谓词对列表的某些元素成立，则返回真，否则返回假。

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
        // Creating a list
        val m1 = List(1, 2, 3, 4, 5)

        // Applying exists method
        val result = m1.exists(y => {y % 3 == 0})

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
        // Creating a list
        val m1 = List(1, 2, 3, 4, 5)

        // Applying exists method
        val result = m1.exists(y => {y % 9 == 0})

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```