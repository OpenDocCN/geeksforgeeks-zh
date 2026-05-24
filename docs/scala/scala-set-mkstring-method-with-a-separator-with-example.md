# 带分隔符的 Scala Set mkString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-MK string-method-with-separator-with-example/](https://www.geeksforgeeks.org/scala-set-mkstring-method-with-a-separator-with-example/)

**mkString()** 方法用于显示字符串中集合的所有元素以及分隔符。

> **方法定义:**def mkString(sep:String):String
> 
> **返回类型:**它返回字符串中集合的所有元素以及分隔符。

**示例#1:**

```scala
// Scala program of mkString() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set(1, 2, 3, 4) 

        // Applying mkString method 
        val result = s1.mkString(", ")

        // Display output
        println(result)
    } 
} 
```

**Output:**

```scala
1, 2, 3, 4

```

**例 2:**

```scala
// Scala program of mkString() 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 
        // Creating a set 
        val s1 = Set("Geeks", "Will", "Rule") 

        // Applying mkString method 
        val result = s1.mkString(" ")

        // Display output
        println(result)
    } 
}
```

**Output:**

```scala
Geeks Will Rule

```