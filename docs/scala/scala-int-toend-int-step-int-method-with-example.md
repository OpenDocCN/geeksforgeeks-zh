# Scala Int to(end: int，step: int)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-to end-int-step-int-method-with-example/](https://www.geeksforgeeks.org/scala-int-toend-int-step-int-method-with-example/)

**到(end: int，step: int)** 方法用于返回从所述整数到“end”的范围，该范围在参数列表中给出，并且在参数列表中也指定了某个步骤。

> **方法定义:**定义为(结束:Int，步骤:Int):包含
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
        val result = 5.to(10, 2) 

        // Displays output 
        println(result) 

    } 
}  
```

**Output:**

```scala
Range(5, 7, 9)

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
        val result = (0).to(9, 3) 

        // Displays output 
        println(result) 

    } 
}  
```

**Output:**

```scala
Range(0, 3, 6, 9)

```