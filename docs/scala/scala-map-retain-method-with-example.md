# Scala Map retain()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-retain-method-with-example/](https://www.geeksforgeeks.org/scala-map-retain-method-with-example/)

**保留()**方法用于保留满足所述条件的所有地图对。

> **方法定义:** def retain(p: (A，B)=>Boolean:map . this . type
> 
> **返回类型:**返回满足所述谓词的映射的所有“键值”对。

**示例#1:**

```scala
// Scala program of retain()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a mutable map
        val m1 = scala.collection.mutable.Map(3 -> "geeks", 
                                    1 -> "for", 2 -> "cs")

        // Applying retain method
        val result = m1.retain((key,value) => key > 1)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(2 -> cs, 3 -> geeks)

```

**例:2#**

```scala
// Scala program of retain()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a mutable map
        val m1 = scala.collection.mutable.Map(3 -> "geeks",
                                    1 -> "for", 1 -> "cs")

        // Applying retain method
        val result = m1.retain((key,value) => key > 1)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(3 -> geeks)

```