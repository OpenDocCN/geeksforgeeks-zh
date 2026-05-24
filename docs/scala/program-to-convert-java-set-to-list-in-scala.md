# 在 Scala 中将 Java Set 转换为 List 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-to-list-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-to-list-in-scala/)

利用 Scala 中 java 的 *toList* 方法，可以将一个 Java 集合转换为 Scala 中的列表。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set 
// to List in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

    // Creating set in Java
    val set = new java.util.HashSet[String]()

    // Adding string to the set
    set.add("GfG")
    set.add("is a")
    set.add("CS-portal")

    // Converting set to list
    val list = set.toList

    // Displays set
    println(list)

}
}
```

**Output:**

```scala
List(GfG, is a, CS-portal)

```

因此，返回一个字符串列表。这里，首先创建一个集合，利用 *add* 方法向其中添加字符串元素。之后利用*列表*方法将所述集合转换为字符串列表。
**例:2#**

```scala
// Scala program to convert Java set 
// to List in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

    // Creating set in Java
    val set = new java.util.HashSet[String]()

    // Adding string to the set
    set.add("Nidhi")
    set.add("is an")
    set.add("Author")

    // Converting set to list
    val list = set.toList

    // Displays set
    println(list)

}
}
```

**Output:**

```scala
List(nidhi, Author, is an)

```

它与上面的例子相同，但是这里单词较多的字符串比单词较少的字符串显示得晚。