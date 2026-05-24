# Scala Set equals()方法，示例

> 原文: [https://www.geeksforgeeks.org/scala-set-equals-method-with-example/](https://www.geeksforgeeks.org/scala-set-equals-method-with-example/)

利用`equals()`方法检查两组元素是否相同。

## 方法定义

> **方法定义:** `def equals(that: Any): Boolean`
>
> **返回类型:** 如果两个集合的元素相同，则返回`true`，否则返回`false`。

## 示例#1

```scala
// Scala program of equals()
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating sets
        val s1 = Set("geeks", "for", "cs")
        val s2 = Set("cs", "for", "geeks")

        // Applying equals method
        val result = s1.equals(s2)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
true
```

## 示例#2

```scala
// Scala program of equals()
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating sets
        val s1 = Set(11, 10, 2019)
        val s2 = Set(9, 10, 2018)

        // Applying equals method
        val result = s1.equals(s2)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
false
```