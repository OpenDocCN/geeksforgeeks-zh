# Scala `Int >=(x: Int)` 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-int-x-int-method-with-example-12/](https://www.geeksforgeeks.org/scala-int-x-int-method-with-example-12/)

如果指定的 `Int` 值大于或等于另一个 `Int` 值，则使用 `>=(x: Int)` 方法返回 `true`，否则返回 `false`。

> **方法定义:** `(Int_Value).>=(int_Value)`
> **返回类型:** 如果指定的 `Int` 值大于或等于另一个 `Int` 值，则返回 `true`，否则返回 `false`。

## 示例 1

```scala
// Scala program of Int >=(x: Int)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying Int >=(x: Int) function
        val result = (66).>=(55)

// Displays output
        println(result)

}
}
```

**输出:**

```scala
true
```

## 示例 2

```scala
// Scala program of Int >=(x: Int)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying Int >=(x: Int) function
        val result = (50).>=(60)

// Displays output
        println(result)

}
}
```

**输出:**

```scala
false
```