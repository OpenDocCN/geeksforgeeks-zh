# Scala Map toSeq()方法，带示例

> 原文:[https://www . geesforgeks . org/Scala-map-toseq-method-with-example/](https://www.geeksforgeeks.org/scala-map-toseq-method-with-example/)

**toSeq()** 方法用于显示 Scala 映射中的序列。

> **方法定义:**def to eq:Seq[A]
> 
> **返回类型:**从指定的地图返回一个序列。

**示例#1:**

```scala
// Scala program of toSeq()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 4 -> "for")

        // Applying toSeq method
        val result = m1.toSeq

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
ArrayBuffer((3, geeks), (4, for))

```

**例 2:**

```scala
// Scala program of toSeq()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying toSeq method
        val result = m1.toSeq

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
ArrayBuffer((3, geeks), (4, for), (2, cs))

```