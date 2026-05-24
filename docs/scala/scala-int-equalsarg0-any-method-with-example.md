# Scala Int 等于(arg0: Any)方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-equalsarg 0-任何带有示例的方法/](https://www.geeksforgeeks.org/scala-int-equalsarg0-any-method-with-example/)

如果两个指定的 int 值相等，则使用 **equals(arg0: Any)** 方法返回 true，否则返回 false。

> **方法定义:** def 等于(arg0: Any):布尔值
> 
> **返回类型:**如果两个指定的 int 值相等，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int equals
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying equals method 
        val result = (66).equals(22)

        // Displays output 
        println(result) 

    } 
}  
```

**Output:**

```scala
false

```

**例 2:**

```scala
// Scala program of Int equals
// method 

// Creating object 
object GfG 
{  

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying equals method 
        val result = (22).equals(22)

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
true

```