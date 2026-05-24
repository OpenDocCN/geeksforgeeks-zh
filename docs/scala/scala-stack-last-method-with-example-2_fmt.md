# Scala Stack isEmpty()方法示例

> 原文: [`https://www.geeksforgeeks.org/scala-stack-last-method-with-example-2/`](https://www.geeksforgeeks.org/scala-stack-last-method-with-example-2/)

在 Scala `Stack` 类中，`isEmpty()` 用于检查堆栈是否为空。

## 方法定义
```scala
def isEmpty: Boolean
```

**返回类型:** 如果堆栈为空则返回 `true`，否则返回 `false`。

## 示例 #1

```scala
// Scala program of isEmpty() 
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

// Applying isEmpty method  
        val result = s1.isEmpty

// Display output 
        print("The stack is empty: " + result)

} 
} 
```

**Output:**

```scala
Stack(1, 3, 2, 7, 6, 5)
The stack is empty: false
```

## 示例 #2

```scala
// Scala program of isEmpty() 
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
        val s1 = Stack()

// Print the stack 
        println(s1)

// Applying isEmpty method  
        val result = s1.isEmpty

// Display output 
        print("The stack is empty: " + result)

} 
} 
```

**Output:**

```scala
Stack()
The stack is empty: true
```