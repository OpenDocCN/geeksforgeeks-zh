# Scala List forall()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-list-forall-method-with-example/](https://www.geeksforgeeks.org/scala-list-forall-method-with-example/)

使用 `forall()` 方法检查给定的谓词是否满足列表的所有元素。

**方法定义:** 定义为 `forall(p: (A) => Boolean): Boolean`

**返回类型:** 如果声明的谓词对列表的所有元素都成立，则返回 `true`，否则返回 `false`。

## 示例#1

```scala
// Scala program of forall()
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {
        // Creating a list
        val m1 = List(3, 6, 12, 9, 21)

        // Applying forall method
        val result = m1.forall(y => {y % 3 == 0})

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
true
```

## 例 2

```scala
// Scala program of forall()
// method

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {
        // Creating a list
        val m1 = List(3, 6, 2, 9, 21)

        // Applying forall method
        val result = m1.forall(y => {y % 3 == 0})

        // Displays output
        println(result)
    }
}
```

**Output:**

```scala
false
```