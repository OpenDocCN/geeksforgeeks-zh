# Scala Map addString()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-map-add string-method-with-example/](https://www.geeksforgeeks.org/scala-map-addstring-method-with-example/)

**添加字符串()**方法用于将地图元素添加到字符串生成器中。

> **方法定义:**def addString(b:StringBuilder):StringBuilder
> 
> **返回类型:**返回字符串生成器中的元素。

**示例#1:**

```scala
// Scala program of addString()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a map
        val m1 = Map("geeks" -> 5, "for" -> 3, "cs" -> 2) 

        // Applying addString method
        val result = m1.addString(new StringBuilder()) 

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
geeks -> 5for -> 3cs -> 2

```