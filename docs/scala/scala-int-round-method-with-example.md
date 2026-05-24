# Scala Int round()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-round-method-with-example/](https://www.geeksforgeeks.org/scala-int-round-method-with-example/)

**round()** 方法用于返回指定 int 值的舍入值。这种方法用于避免通过浮子绕行时意外损失精度。

> **方法定义:**定义回合:整数
> 
> **返回类型:**返回指定 int 值的舍入值。

**示例#1:**

```scala
// Scala program of Int round
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying round method 
        val result = (5).round

        // Displays output 
        println(result) 

    } 
}  
```

**Output:**

```scala
5

```

**例 2:**

```scala
// Scala program of Int round
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying round method 
        val result = (5.8).round

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
6

```