# 在 Scala 中连接两个地图

> 原文:[https://www . geeksforgeeks . org/concatenate-Scala 中的两个地图/](https://www.geeksforgeeks.org/concatenate-two-maps-in-scala/)

Scala 映射的拼接是利用**+**运算符得到的。
**语法:**

```scala
def ++(xs: Map[(A, B)]): Map[A, B]

```

**返回类型:**
它通过连接两个地图返回一个地图，但是它将相同的键分开。
**示例#1:**

```scala
// Scala program of concatenating
// two maps

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating the first map
        val m1 = Map("Nidhi" -> 23, "Rahul" -> 18) 

        // Creating the second map
        val m2 = Map("Geeta" -> 22, "Rahul" -> 18) 

        // Applying ++ operator
        val result = m1.++(m2)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(Nidhi -> 23, Rahul -> 18, Geeta -> 22)

```

正如我们在上面的例子中看到的，我们通过使用 **++** 操作符连接了两个地图。
**例 2:**

```scala
// Scala program of concatenating
// two maps

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating the first map
        val m1 = Map("geeks" -> 5, "for" -> 3) 

        // Creating the second map
        val m2 = Map("geeks" -> 5, "cs" -> 2) 

        // Applying ++ operator
        val result = m1.++(m2)

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
Map(geeks -> 5, for -> 3, cs -> 2)

```