# Scala Set subtof()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-sub tof-method-with-example/](https://www.geeksforgeeks.org/scala-set-subsetof-method-with-example/)

**subtof()**方法用于测试一个集合是否是另一个集合的子集。

> **方法定义:**def subtof(即:集合[A]):布尔值
> 
> **返回类型:**如果一个集合是另一个集合的子集，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of subsetOf() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(4, 12, 2, 31) 

        val s2 = Set(4, 12)

        // Applying subsetOf method 
        val result = s2.subsetOf(s1)

        // Display output
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
// Scala program of subsetOf() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(4, 12, 2, 31) 

        val s2 = Set(4, 12)

        // Applying subsetOf method 
        val result = s1.subsetOf(s2)

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
false

```