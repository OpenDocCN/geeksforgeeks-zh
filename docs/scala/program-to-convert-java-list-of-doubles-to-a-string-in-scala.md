# 在 Scala 中将 Java 双精度列表转换为字符串的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-double-to-string-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-of-doubles-to-a-string-in-scala/)

利用 Scala 中 java 的 *toString* 方法，可以将一个 Java 的双精度列表转换成 Scala 中的字符串。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便进行转换。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list
// to a String in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

// Creating list of doubles in Java
val list = new java.util.ArrayList[Double]()

// Adding doubles to the list
list.add(1.34)
list.add(9.01)
list.add(7.1)

// Converting list to a String
val str = list.toString

// Displays output
println(str)

}
}
```

**Output:**

```scala
[1.34, 9.01, 7.1]

```

**例:2#**

```scala
// Scala program to convert Java list
// to a String in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

// Creating list of doubles in Java
val list = new java.util.ArrayList[Double]()

// Adding doubles to the list
list.add(7.12)
list.add(6.12)
list.add(9.12)

// Converting list to a String
val str = list.toString

// Displays output
println(str)

}
}
```

**Output:**

```scala
[7.12, 6.12, 9.12]

```

**参考:**
[https://alvinalexander . com/Scala/how-to-from-Java-collections-convert-in-Scala-interaction](https://alvinalexander.com/scala/how-to-go-from-java-collections-convert-in-scala-interact)。