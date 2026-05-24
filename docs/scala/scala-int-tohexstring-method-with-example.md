# Scala Int to exString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-to exstring-method-with-example/](https://www.geeksforgeeks.org/scala-int-tohexstring-method-with-example/)

利用**to exstring()**方法返回指定整数值的六进制形式。

> **方法定义:**定义为字符串:字符串
> 
> **返回类型:**返回指定整数值的六进制形式。

**示例#1:**

```scala
// Scala program of Int toHexString()
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 
        // Applying toHexString() method  
        val result = (5).toHexString

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
// Scala program of Int toHexString()
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 
        // Applying toHexString() method  
        val result = (18).toHexString

        // Displays output 
        println(result) 

    } 
}   
```

**Output:**

```scala
12

```