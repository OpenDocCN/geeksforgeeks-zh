# Scala 集合包含()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-contains-method-with-example/](https://www.geeksforgeeks.org/scala-set-contains-method-with-example/)

contains()方法用于检查 not 集合中是否存在元素。

> **方法定义:** def 包含(elem: A):布尔值
> 
> **返回类型:**如果元素存在于集合中，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of contains() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43, 1, 72) 

        // Applying contains() method 
        val result = s1.contains(1)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of contains() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(41, 12, 23, 43, 1, 72) 

        // Applying contains() method 
        val result = s1.contains(10)

        // Display output
        print(result)   

    } 
} 
```

**Output:**

```scala
false

```