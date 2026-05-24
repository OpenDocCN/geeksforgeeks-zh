# Scala String replaceFirst()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-replace first-method-with-example/](https://www.geeksforgeeks.org/scala-string-replacefirst-method-with-example/)

**replaceFirst()** 方法与 *replaceAll* 相同，但这里只替换所述子字符串的第一次出现。

> **方法定义:**String replace first(String regex，String replace)
> **返回类型:**用我们提供的字符串替换声明正则表达式的第一个外观后返回声明字符串。

**示例#1:**

```scala
// Scala program of replaceFirst()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying replaceFirst method
        val result = "csoNidhimsoSingh".replaceFirst(".so", "##")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
##NidhimsoSingh

```

**例 2:**

```scala
// Scala program of replaceFirst()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying replaceFirst method
        val result = "NidhimsoSinghcso".replaceFirst(".so", "*")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
Nidhi*Singhcso

```

**示例#3:**

```scala
// Scala program of replaceFirst()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying replaceFirst method
        val result = "fsoNidhimsoSinghcso".replaceFirst(".so", "*")

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
*NidhimsoSinghcso

```