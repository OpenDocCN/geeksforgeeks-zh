# 将 Java 字符串列表转换为 Scala 中可遍历的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-to-traversable-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-strings-to-traversable-in-scala/)

通过利用 Scala 中 java 的 *toTraversable* 方法，可以将 Java 字符串列表转换为 Scala 中的 Traversable 集合。在这里，您需要导入 Scala 的 JavaConversions 对象，以便进行转换。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to a Traversable in Scala

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
list.add("i")
list.add("am")
list.add("good")

// Converting list to a Traversable 
val tra= list.toTraversable

// Displays traversable 
println(tra)

}
}
```

**Output:**

```scala
Buffer(i, am, good)

```

这里，所述输出与给定列表中所述的顺序相同。
**例:2#**

```scala
// Scala program to convert Java list
// to a Traversable in Scala

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
list.add("i")
list.add("am a")
list.add("girl")

// Converting list to a Traversable 
val tra= list.toTraversable

// Displays traversable 
println(tra)

}
}
```

**Output:**

```scala
Buffer(i, am a, girl)

```

这里，首先显示字数较少的字符串，最后显示长度较大的字符串。
**参考:**
[https://alvinalexander . com/Scala/how-to-from-Java-collections-convert-in-Scala-interaction](https://alvinalexander.com/scala/how-to-go-from-java-collections-convert-in-scala-interact)。