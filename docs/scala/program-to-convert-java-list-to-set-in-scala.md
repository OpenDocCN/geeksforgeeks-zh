# 将 Java 列表转换为 Scala 中 Set 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-to-set-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-to-set-in-scala/)

利用 Scala 中 java 的 *toSet* 方法，可以将一个 Java 列表转换为 Scala 中的 Set。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to Set in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list in Java
        val list = new java.util.ArrayList[String]()

        // Adding string to the list
        list.add("GfG")

        // Converting list to set
        val set = list.toSet

        // Displays set
        println(set)

    }
}
```

**Output:**

```scala
Set(GfG)

```

因此，返回一组字符串。这里，首先创建一个列表，使用 *add* 方法将字符串元素添加到列表中。之后，使用*设置*方法将所述列表转换为字符串集。
**例:2#**

```scala
// Scala program to convert Java list 
// to Set in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating list in Java
        val list = new java.util.ArrayList[String]()

        // Adding string to the list
        list.add("GfG")
        list.add("is a")
        list.add("CS-portal")

        // Converting list to set
        val set = list.toSet

        // Displays set
        println(set)

    }
}
```

**Output:**

```scala
Set(GfG, is a, CS-portal)

```

它与上面的例子相同，但是这里在所述列表中增加了一个元素，然后在这里作为输出返回到集合中。