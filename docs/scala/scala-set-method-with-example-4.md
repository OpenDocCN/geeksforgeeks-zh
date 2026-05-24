# Scala Set & ~()法同例

> 原文:[https://www . geeksforgeeks . org/Scala-set-method-with-example-4/](https://www.geeksforgeeks.org/scala-set-method-with-example-4/)

利用 **& ~()** 方法在两个给定集合之间的差之后创建由元素组成的新集合。

> **方法定义:** def & ~(即:集[A]):集[A]
> 
> **返回类型:**返回由两个给定集合之间的差之后的元素组成的集合。

**示例#1:**

```scala
// Scala program of &~() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43, 1, 72) 

        val s2 = Set(1, 100, 5, 12, 23)

        // Applying &~() method 
        val result = s1.&~(s2)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Set(41, 72, 43)

```

**例 2:**

```scala
// Scala program of &~() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 5, 3, 4) 

        val s2 = Set(2, 4)

        // Applying &~() method 
        val result = s2.&~(s1)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
Set()

```