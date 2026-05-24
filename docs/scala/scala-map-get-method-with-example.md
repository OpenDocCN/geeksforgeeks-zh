# Scala Map get()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-get-method-with-example/](https://www.geeksforgeeks.org/scala-map-get-method-with-example/)

利用 **get()** 方法给出与地图关键点相关的值。这些值在这里作为一个选项返回，即以“部分”或“无”的形式返回。

> **方法定义:** def get(键:A):Option【B】
> 
> **返回类型:**返回方法中给定值对应的键作为参数。

**示例#1:**

```scala
// Scala program of get()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2) 

        // Applying get method
        val result = m1.get("for")

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
Some(3)

```