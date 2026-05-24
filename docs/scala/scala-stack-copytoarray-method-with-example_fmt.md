# Scala Stack copyToArray()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-stack-copytoarray-method-with-example/](https://www.geeksforgeeks.org/scala-stack-copytoarray-method-with-example/)

## 方法介绍
在 Scala `Stack` 类中，`copyToArray()` 方法用于将堆栈的元素复制到数组中。

## 方法定义与参数
> **方法定义:** `def copyToArray[B >: A](xs: Array[B], start: Int, len: Int): Int`
>
> **参数:**
> - `xs`: 表示复制元素的数组。
> - `start`: 表示复制开始的索引。其默认值为 0。
> - `len`: 表示要复制的元素数量。它的默认值是集合的长度。
>
> **返回类型:** 它将堆栈的元素返回到数组中。

## 示例 1

### 代码
```scala
// Scala program of copyToArray() method

// Import Stack
import scala.collection.mutable._

// Creating object
object GfG {

  // Main method
  def main(args: Array[String]) {

    // Creating a stack
    val s1 = Stack(1, 2, 3)

    // Print the stack
    println(s1)

    // Creating an array
    val arr: Array[Int] = Array(0, 0, 0, 0, 0)

    // Applying copyToArray method
    s1.copyToArray(arr)

    // Displays output
    println("Elements in the array: ")

    for (elem <- arr)
      print(elem + " ")
  }
}
```

### 输出
```scala
Stack(1, 2, 3)
Elements in the array:
1 2 3 0 0
```

## 示例 2

### 代码
```scala
// Scala program of copyToArray() method

// Import Stack
import scala.collection.mutable._

// Creating object
object GfG {

  // Main method
  def main(args: Array[String]) {

    // Creating a stack
    val s1 = Stack(1, 2, 3)

    // Print the stack
    println(s1)

    // Creating an array
    val arr: Array[Int] = Array(0, 0, 0, 0, 0)

    // Applying copyToArray method
    s1.copyToArray(arr, 1, 2)

    // Displays output
    println("Elements in the array: ")

    for (elem <- arr)
      print(elem + " ")
  }
}
```

### 输出
```scala
Stack(1, 2, 3)
Elements in the array:
0 1 2 0 0
```