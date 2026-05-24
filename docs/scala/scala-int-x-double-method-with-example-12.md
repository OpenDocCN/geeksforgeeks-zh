# Scala Int > =(x: Double)方法，示例

> 原文:[https://www . geesforgeks . org/Scala-int-x-double-method-with-example-12/](https://www.geeksforgeeks.org/scala-int-x-double-method-with-example-12/)

如果指定的 int 值大于或等于 Double 值，则使用 **> =(x: Double)** 方法返回 true，否则返回 false。

> **方法定义:** (Int_Value)。> =(Double_Value)
> **返回类型:**如果指定的 int 值大于或等于 Double 值，则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of Int >=(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >=(x: Double) function
        val result = (66).>=(55)

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
// Scala program of Int >=(x: Double)
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Applying Int >=(x: Double) function
        val result = (50).>=(60)

        // Displays output
        println(result)

    }
} 
```

**Output:**

```scala
false

```