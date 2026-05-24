# Scala String replaceAll()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-replace all-method-with-example/](https://www.geeksforgeeks.org/scala-string-replaceall-method-with-example/)

**replaceAll()** 方法用于用我们在参数列表中提供的字符串替换与正则表达式匹配的字符串的每个指定子字符串。

> **方法定义:**String replace all(String regex，String replace)
> **返回类型:**用我们提供的字符串替换所述子字符串后返回所述字符串。

**示例#1:**

```scala
// Scala program of replaceAll()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying replaceAll method
        val result = "csoNidhimso".replaceAll(".so", "##")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
##Nidhi##

```

**例 2:**

```scala
// Scala program of replaceAll()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying replaceAll method
        val result = "csoNidhimsoSingh ".replaceAll(".so", "##")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
##Nidhi##Singh

```