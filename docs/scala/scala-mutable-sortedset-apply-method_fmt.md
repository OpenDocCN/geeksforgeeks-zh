# Scala 可变 SortedSet apply()方法

> 原文: [https://www.geeksforgeeks.org/scala-mutable-sortedset-apply-method/](https://www.geeksforgeeks.org/scala-mutable-sortedset-apply-method/)

在 Scala 可变集合中，`apply()` 方法用于测试 SortedSet 中是否存在某些元素。

## 方法定义与返回类型

**方法定义:** `def apply(elem: A)`

**返回类型:** 如果 SortedSet 中存在某些元素，则返回 `true`，否则返回 `false`。

## 示例

### 示例#1:

```scala
// Scala program of apply()
// method
import scala.collection.mutable.SortedSet

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    {

// Creating SortedSets 
        val s1 = SortedSet(1, 2, 3, 4, 5)

// Applying apply method 
        val result = s1.apply(3)

// Displays output 
        println(result)

} 
} 
```

**Output:**

```scala
true
```

### 示例#2:

```scala
// Scala program of apply()
// method
import scala.collection.mutable.SortedSet

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    {

// Creating SortedSets 
        val s1 = SortedSet(1, 2, 3, 4, 5)

// Applying apply method 
        val result = s1.apply(10)

// Displays output 
        println(result)

} 
} 
```

**Output:**

```scala
false
```