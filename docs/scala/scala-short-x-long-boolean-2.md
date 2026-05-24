# 斯卡拉短> =(x:长):布尔

> 原文:[https://www.geeksforgeeks.org/scala-short-x-long-boolean-2/](https://www.geeksforgeeks.org/scala-short-x-long-boolean-2/)

短，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的子类型。如果该值大于或等于 x，则使用> =(x: Long)方法返回 true，否则返回 false。

> **方法定义:** def > =(x: Long):布尔值
> 
> **返回类型:**如果该值大于或等于 x，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of Short >=(x: Long) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short >=(x: Long) function 
        val result = (998.toShort).>=(999:Long)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
false

```

**例 2:**

```scala
// Scala program of Short >=(x: Long) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short >=(x: Long) function 
        val result = (102.toShort).>=(101:Long)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```scala
true

```