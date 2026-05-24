# Scala List drop()方法示例

> 原文:[https://www . geesforgeks . org/Scala-list-drop-method-with-example/](https://www.geeksforgeeks.org/scala-list-drop-method-with-example/)

**drop()** 方法属于类*列表*的值成员。它用于选择列表中除第一个 *n* 元素之外的所有元素。

> **方法定义:** def drop(n: Int):列表[A]
> 
> 其中， *n* 是要从指定序列中删除的元素数量。
> 
> **返回类型:**返回列表中除第一个 *n* 之外的所有元素。

**示例#1:**

```scala

// Scala program of drop()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a List 
        val list = List("a", "b", "c", "d", "e", "f")

        // Applying drop method 
        val result = list.drop(4)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List(e, f)

```

**例 2:**

```scala
// Scala program of drop()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a List 
        val list = List(1, 2, 3, 4, 5, 6)

        // Applying drop method 
        val result = list.drop(2)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
List(3, 4, 5, 6)

```