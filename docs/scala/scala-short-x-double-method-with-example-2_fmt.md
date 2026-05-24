# Scala Short.*(x: Double) 方法详解

> 原文: `https://www.geeksforgeeks.org/scala-short-x-double-method-with-example-2/`

利用 `*(x: Double)` 方法求所述 Short 值与 Double 类型的 `x` 的乘积。

## 方法定义与返回类型

**方法定义:**
```scala
def *(x: Double): Double
```

**返回类型:** 返回 `Double`。

## 示例

### 示例 1

```scala
// Scala program of *(x: Double)
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying *(x: Double) method
        val result = (889).*(10.4311)

        // Displays output
        println(result)
    }
}
```

**输出:**
```scala
9273.2479
```

### 示例 2

```scala
// Scala program of *(x: Double)
// method

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying *(x: Double) method
        val result = (1000).*(54.123)

        // Displays output
        println(result)
    }
}
```

**输出:**
```scala
54123.0
```