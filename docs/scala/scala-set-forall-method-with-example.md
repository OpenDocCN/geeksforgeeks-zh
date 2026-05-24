# Scala Set forall()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-for all-method-with-example/](https://www.geeksforgeeks.org/scala-set-forall-method-with-example/)

**forall()** 方法用于检查给定的谓词是否满足集合的所有元素。

> **方法定义:**定义为 all(p: (A) = >布尔型:布尔型
> 
> **返回类型:**如果所述谓词对集合的所有元素都成立，则返回真，否则返回假。

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
        // Creating a set 
        val s1 = Set(3, 6, 12, 9, 21) 

        // Applying forall method 
        val result = s1.forall(y => {y % 3 == 0}) 

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
        // Creating a set 
        val s1 = Set(3, 7, 12, 9, 21) 

        // Applying forall method 
        val result = s1.forall(y => {y % 3 == 0}) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
false

```