# Scala Int to(end: Int)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-to end-int-method-with-example/](https://www.geeksforgeeks.org/scala-int-toend-int-method-with-example/)

**到(end: Int)** 方法用于返回从所述 Int 到‘end’的范围，该范围在参数列表中给出，但是在这里“step”没有在参数列表中指定。

> **方法定义:**定义为(结束:Int):包含
> 
> **返回类型:**返回范围。

**示例#1:**

```scala
// Scala program of Int to() 
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 
        // Applying to() method  
        val result = 5.to(10) 

        // Displays output 
        println(result) 

    } 
}  
```

**Output:**

```scala
Range(5, 6, 7, 8, 9, 10)

```

**例 2:**

```scala
// Scala program of Int to() 
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 
        // Applying to() method  
        val result = 20.to(25) 

        // Displays output 
        println(result) 

    } 
}  
```

**Output:**

```scala
Range(20, 21, 22, 23, 24, 25)

```