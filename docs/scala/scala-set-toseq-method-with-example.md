# Scala Set toSeq()方法示例

> 原文:[https://www . geesforgeks . org/Scala-set-toseq-method-with-example/](https://www.geeksforgeeks.org/scala-set-toseq-method-with-example/)

**toSeq()** 方法用于返回包含集合所有元素的序列。

> **方法定义:**def to eq:Seq[A]
> 
> **返回类型:**返回一个包含集合所有元素的序列。

**示例#1:**

```scala
// Scala program of toSeq() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4, 5, 6) 

        // Applying toSeq method 
        val result = s1.toSeq

        // Display output
        for (ele <- result)
            println(ele)

    } 
} 
```

**Output:**

```scala
5
1
6
2
3
4

```

**例 2:**

```scala
// Scala program of toSeq() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43, 1, 72) 

        // Applying toSeq method 
        val result = s1.toSeq

        // Display output
        for (ele <- result)
            println(ele)

    } 
} 
```

**Output:**

```scala
1
41
12
72
43
23

```