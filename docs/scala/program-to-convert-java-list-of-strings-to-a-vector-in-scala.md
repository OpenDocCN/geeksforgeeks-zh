# 在 Scala 中将 Java 字符串列表转换成向量的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-to-vector-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-strings-to-a-vector-in-scala/)

利用 Scala 中 java 的 *toVector* 方法，可以将 Java 字符串列表转换为 Scala 中的向量。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使这个转换工作，否则会发生错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

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

        // Creating list of Strings in Java
        val list = new java.util.ArrayList[String]()

        // Adding Strings to the list
        list.add("Geeks")
        list.add("for")
        list.add("Geeks")

        // Converting list to a Vector 
        val vec= list.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(Geeks, for, Geeks)

```

因此，结果输出的顺序与上面列表中的顺序相同，重复的输出也不会被删除。
**例:2#**

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

        // Creating list of Strings in Java
        val list = new java.util.ArrayList[String]()

        // Adding Strings to the list
        list.add("My")
        list.add("name is")
        list.add("Nidhi")

        // Converting list to a Vector 
        val vec= list.toVector

        // Displays vector
        println(vec)

    }
}
```

**Output:**

```scala
Vector(My, name is, Nidhi)

```

这里，所述的字符串没有按正确的顺序排列，因此结果输出也没有按正确的顺序排列。这里，首先显示单词数较多的字符串。