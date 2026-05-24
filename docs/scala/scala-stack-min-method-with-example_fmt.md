# Scala Stack min()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-stack-min-method-with-example/](https://www.geeksforgeeks.org/scala-stack-min-method-with-example/)

在 Scala `Stack` 类中，`min()` 方法用于返回堆栈中的最小元素。

## 方法定义

> **定义:** `def min: A`
>
> **返回类型:** 返回栈中最小的元素。

## 示例

### 示例#1

```scala
// Scala program of min()
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
        val s1 = Stack(5, 3, 2, 7, 6, 1)

// Print the stack
        println(s1)

// Applying min method
        val result = s1.min

// Display output
        print("The smallest element of the stack: " + result)

}
}
```

**输出:**

```scala
Stack(5, 3, 2, 7, 6, 1)
The smallest element of the stack: 1
```

### 示例#2

```scala
// Scala program of min()
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
        val s1 = Stack(15, 13, 12, 7, 6, 11)

// Print the stack
        println(s1)

// Applying min method
        val result = s1.min

// Display output
        print("The smallest element of the stack: " + result)

}
}
```

**输出:**

```scala
Stack(15, 13, 12, 7, 6, 11)
The smallest element of the stack: 6
```