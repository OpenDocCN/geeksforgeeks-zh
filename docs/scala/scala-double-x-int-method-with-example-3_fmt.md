# Scala Double `+(x: Int)` 方法示例

> 原文: [https://www.geeksforgeeks.org/scala-double-x-int-method-with-example-3/](https://www.geeksforgeeks.org/scala-double-x-int-method-with-example-3/)

`+(x: Int)` 方法用来求指定的 `Double` 和参数中给定的 `Int` 类型的值 `x` 的和。

> **语法:** `def +(x: Int): Double`
> **返回:** 它返回指定 `Double` 和给定 `Int` 类型值 `x` 的和。

## 例 1:

```scala
// Scala program of +(x: Int) 
// method

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    {

// Applying +(x: Int) method  
        val result = 5.39432456.+(32)

// Displays output 
        println(result)

} 
}  
```

**输出:**

```scala
37.39432456
```

## 例 2:

```scala
// Scala program of +(x: Int) 
// method

// Creating object 
object GfG 
{

// Main method 
    def main(args:Array[String]) 
    {

// Applying +(x: Int) method  
        val result = 5.39432456.+(78)

// Displays output 
        println(result)

} 
}  
```

**输出:**

```scala
83.39432456
```