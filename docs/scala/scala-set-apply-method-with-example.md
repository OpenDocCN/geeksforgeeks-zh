# Scala Set apply()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-set-apply-method-with-example/](https://www.geeksforgeeks.org/scala-set-apply-method-with-example/)

利用 **apply()** 方法测试集合中是否存在某些元素。

> **方法定义:**定义应用(元素:A)
> 
> **返回类型:**如果集合中存在某些元素，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of apply()
// method

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating sets 
        val s1 = Set(1, 2, 3, 4, 5) 

        // Applying apply method 
        val result = s1.apply(3) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
true

```

**例 2:**

```scala
// Scala program of apply()
// method

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating sets 
        val s1 = Set(1, 2, 3, 4, 5) 

        // Applying apply method 
        val result = s1.apply(10) 

        // Displays output 
        println(result) 

    } 
} 
```

**Output:**

```scala
false

```