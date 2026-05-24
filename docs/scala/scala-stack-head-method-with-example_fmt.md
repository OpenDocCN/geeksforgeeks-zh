# Scala Stack head()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-stack-head-method-with-example/](https://www.geeksforgeeks.org/scala-stack-head-method-with-example/)

在 Scala `Stack` 类中，`head()` 方法用于返回堆栈的顶部元素。

> **方法定义:** `def head: A`
>
> **返回类型:** 返回栈顶元素。

## 示例 1

```scala
// Scala program of head()
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

// Applying head method
        val result = s1.head

// Display output
        print("Top element of the stack: " + result)

}
}
```

**输出:**

```scala
Stack(1, 3, 2, 7, 6, 5)
Top element of the stack: 1
```

## 示例 2

```scala
// Scala program of head()
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

// Applying head method
        val result = s1.head

// Display output
        print("Top element of the stack: " + result)

}
}
```

**输出:**

```scala
Stack(5, 3, 2, 7, 6, 1)
Top element of the stack: 5
```