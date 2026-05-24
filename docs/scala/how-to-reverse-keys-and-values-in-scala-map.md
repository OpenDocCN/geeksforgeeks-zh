# 如何反转 Scala 映射中的键和值

> 原文:[https://www . geesforgeks . org/如何在 scala-map 中反转键和值/](https://www.geeksforgeeks.org/how-to-reverse-keys-and-values-in-scala-map/)

在 Scala 中，[映射](https://www.geeksforgeeks.org/scala-map/)与保存键:值对的字典相同。在本文中，我们将学习如何在 Scala 中反转给定映射中的键和值。反转对后，键将变成值，值将变成键。我们可以用 **Scala 来反转地图的键和值，以便理解**。密钥对于反转这些值应该是唯一的，否则我们可能会丢失一些内容。
**语法:**

```scala
val reverseMap = for ((k,v) 下面是在 Scala 映射中反转键和值的例子。**示例#1:** 

```
// Scala program to reverse keys and values

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a map 
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs") 

        // reversing key:value pairs 
        val reverse = for ((k, v) <- m1) yield (v, k)

        // Displays output 
        println(reverse) 

    } 
} 
```scala

**输出:**

```
Map(geeks -> 3, for -> 4, cs -> 2)

```scala

**例 2:** 

```
// Scala program to reverse keys and values

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Creating a map 
        val mapIm = Map("Ajay" -> 30, 
                        "Bhavesh" -> 20, 
                        "Charlie" -> 50) 

        // Applying keySet method 
        val reverse = for ((k, v) <- mapIm) yield (v, k)

        // Displays output 
        println(reverse) 

    } 
} 
```scala

**输出:**

```
Map(30 -> Ajay, 20 -> Bhavesh, 50 -> Charlie)

```scala

->
```