# Scala Map exists()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-exists-method-with-example/](https://www.geeksforgeeks.org/scala-map-exists-method-with-example/)

**exists()** 方法用于检查给定的谓词是否满足映射的元素。

> **方法定义:** def 存在(p:(A，B)) = >布尔型:布尔型
> 
> **返回类型:**如果声明的谓词对地图的某些元素成立，则返回真，否则返回假。

**示例#1:**

```scala
// Scala program of exists()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3)

        // Applying exists method
        val result = m1.exists(x => x._1 == "for" && x._2 == 3)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
true

```

因此，这里陈述的谓词对于第二个**键值**对是真的，所以返回真。
**例 2:**

```scala
// Scala program of exists()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating map
        val m1 = Map("geeks" -> 5, "for" -> 3)

        // Applying exists method
        val result = m1.exists(x => x._1 == "geeks" && x._2 == 3)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
false

```