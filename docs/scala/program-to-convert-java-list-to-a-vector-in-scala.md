# 将 Java 列表转换成 Scala 中的向量的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-to-a-vector-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-to-a-vector-in-scala/)

利用 Scala 中 java 的 *toVector* 方法，可以将 Java 列表转换为 Scala 中的 Vector。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便进行转换，否则会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。

**例:1#**

## 斯卡拉

```scala
// Scala program to convert Java list
// to a Vector in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating list in Java
        val list = new java.util.ArrayList[Int]()

        // Adding integers to the list
        list.add(5)
        list.add(6)

        // Converting list to a Vector
        val vec= list.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:** 

```scala
Vector(5, 6)
```

因此，返回一个整数向量。这里，首先创建一个列表，使用 *add* 方法将 int 元素添加到列表中。之后，使用*到矢量*方法将所述列表转换为矢量。

**例:2#**

## 斯卡拉

```scala
// Scala program to convert Java list
// to a Vector in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Creating list in Java
        val list = new java.util.ArrayList[Int]()

        // Adding integers to the list
        list.add(5)
        list.add(6)
        list.add(1)

        // Converting list to a Vector
        val vec= list.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:** 

```scala
Vector(5, 6, 1)
```

它与上面的例子相同，但是这里在所述列表中增加了一个元素，该元素没有按照正确的顺序排列，然后以向量的形式返回。