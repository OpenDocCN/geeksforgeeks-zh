# Scala Map toArray()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-to array-method-with-example/](https://www.geeksforgeeks.org/scala-map-toarray-method-with-example/)

**toArray()** 方法用于显示 Scala 映射中的数组。

> **方法定义:**定义为数组:数组[(A，B)]
> 
> **返回类型:**从指定的地图返回一个数组。

**示例#1:**

```scala
// Scala program of toArray()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 4 -> "for")

        // Applying toArray method
        val result = m1.toArray

        for ( m5 <-result )
        {
           println(m5 )
        } 

    }
}
```

**Output:**

```scala
(3,geeks)
(4,for)

```

**例 2:**

```scala
// Scala program of toArray()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map(3 -> "geeks", 4 -> "for", 2 -> "cs")

        // Applying toArray method
        val result = m1.toArray

        for ( m5 <-result )
        {
            // Display output
            println(m5 )
        } 

    }
}
```

**Output:**

```scala
(3,geeks)
(4,for)
(2,cs)

```