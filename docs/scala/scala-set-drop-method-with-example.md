# Scala Set drop()方法示例

> 原文:[https://www . geesforgeks . org/Scala-set-drop-method-with-example/](https://www.geeksforgeeks.org/scala-set-drop-method-with-example/)

**drop()** 方法用于删除前‘n’个元素或返回除前‘n’个元素之外的所有元素。

> **方法定义:** def drop(n: Int): Set[A]]
> 
> **返回类型:**返回除前‘n’个元素外的所有元素。

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

        // Creating sets 
        val s1 = Set(5, 1, 2, 3, 4)

        // Applying drop method 
        val s2 = s1.drop(2) 

        // Displays output 
        for(elem <- s2) 
        println(elem) 

    } 
} 
```

**Output:**

```scala
2
3
4

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

        // Creating sets 
        val s1 = Set(5, 1, 2, 3, 4)

        // Applying drop method 
        val s2 = s1.drop(4) 

        // Displays output 
        for(elem <- s2)  
        println(elem) 

    } 
} 
```

**Output:**

```scala
4

```