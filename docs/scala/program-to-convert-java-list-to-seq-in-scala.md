# 在 Scala 中将 Java 列表转换为 Seq 的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-list-to-seq-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-list-to-seq-in-scala/)

利用 Scala 中 java 的 *toSeq* 方法，可以将一个 Java 列表转换成 Scala 中的序列。在这里，您需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作，否则将会出现错误。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java list 
// to Sequence in Scala

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

        // Converting list to Sequence 
        val seq= list.toSeq

        // Displays seq
        println(seq)

    }
}
```

**Output:**

```scala
Buffer(5, 6)

```

因此，返回一个整数序列。这里，首先创建一个列表，使用 *add* 方法将 int 元素添加到列表中。之后，利用*至*方法将所述列表转换为序列。
**例:2#**

```scala
// Scala program to convert Java list 
// to Seq in Scala

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

        // Converting list to a sequence 
        val seq = list.toSeq

        // Displays seq
        println(seq)

    }
}
```

**Output:**

```scala
Buffer(5, 6, 1)

```

它与上面的例子相同，但是这里在所述列表中增加了一个元素，然后它以序列的形式返回。