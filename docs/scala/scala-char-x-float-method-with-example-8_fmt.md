# Scala Char > =(x: Float)方法示例

> 原文: [https://www.geeksforgeeks.org/scala-char-x-float-method-with-example-8/](https://www.geeksforgeeks.org/scala-char-x-float-method-with-example-8/)

使用`>=(x: Float)`方法来查找所述字符值是否大于或等于`x`。`x`的类型必须是`Float`型。

> **方法定义:** `def >=(x: Float): Boolean`
>
> **返回类型:** 如果所述字符值大于或等于`x`，则返回`true`，否则返回`false`。

### 例1

```scala
// Scala program of >=(x: Float)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying >=(x: Float) method
        val result = '\n'.>=(1.4)

// Displays output
        println(result)

}
}
```

**Output:**

```scala
true
```

### 例2

```scala
// Scala program of >=(x: Float)
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying >=(x: Float) method
        val result = '\n'.>=(10.4)

// Displays output
        println(result)

}
}
```

**Output:**

```scala
false
```