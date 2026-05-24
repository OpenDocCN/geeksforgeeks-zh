# Scala List mkString()方法：带开始、分隔符和结束的示例

> 原文：[https://www.geeksforgeeks.org/scala-list-mkstring-method-with-a-start-a-separator-and-an-end-with-example/](https://www.geeksforgeeks.org/scala-list-mkstring-method-with-a-start-a-separator-and-an-end-with-example/)

该方法与 `mkString()` 方法相同，但这里还包括一个开始、一个分隔符和一个结束。

## 方法定义
`def mkString(start: String, sep: String, end: String): String`

## 返回类型
它以字符串形式返回列表的元素，以及指定的开始、分隔符和结束。

我们来看一些例子。

### 例 1
```scala
// Scala program of mkString()
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a list
        val m1 = List(2, 3, 5, 7, 8)

        // Applying mkString method
        val result = m1.mkString("_", "*", "_")

        // Displays output
        println(result)
    }
}
```

**Output:**
```scala
_2*3*5*7*8_
```

### 例 2
```scala
// Scala program of mkString()
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating a list
        val m1 = List(2, 3, 5, 7, 5)

        // Applying mkString method
        val result = m1.mkString("/", "_", "/")

        // Displays output
        println(result)
    }
}
```

**Output:**
```scala
/2_3_5_7_5/
```