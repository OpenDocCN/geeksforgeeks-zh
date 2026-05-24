# Scala Stack exists()方法

> 原文: [https://www.geeksforgeeks.org/scala-stack-exists-method-with-example/](https://www.geeksforgeeks.org/scala-stack-exists-method-with-example/)

在 Scala `Stack` 类中，`exists()` 方法用于检查谓词是否适用于堆栈的任何元素。

## 方法定义

`def exists(p: (A) => Boolean): Boolean`

**返回类型:** 如果谓词对堆栈的任何元素都成立，则返回 `true`，否则返回 `false`。

## 示例 #1

```scala
// Scala program of exists() 
// method

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    {

// Creating stack  
        val s1 = Stack(1, 3, 2, 7, 6, 5)

// Print the stack
        println(s1)

// Applying exists method  
        val result = s1.exists(x => {x % 7 == 0})

// Display output
        println("Element divisible by 7 exists: " + result)
    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Element divisible by 7 exists: true
```

## 示例 #2

```scala
// Scala program of exists() 
// method

// Import Stack 
import scala.collection.mutable._

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    {

// Creating stack  
        val s1 = Stack(1, 3, 2, 7, 6, 5)

// Print the stack
        println(s1)

// Applying exists method  
        val result = s1.exists(x => {x == 10})

// Display output
        println("Element 10 exists: " + result)
    } 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Element 10 exists: false
```