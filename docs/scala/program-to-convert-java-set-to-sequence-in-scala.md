# 在 Scala 中将 Java Set 转换为序列的程序

> 原文:[https://www . geesforgeks . org/program-to-convert-Java-set-to-sequence-in-Scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-to-sequence-in-scala/)

利用 Scala 中 java 的 *toSeq* 方法，可以将一个 Java 集合转换成 Scala 中的一个序列。在这里，我们需要导入 Scala 的 *JavaConversions* 对象，以便使转换工作。
现在，让我们看一些例子，然后详细讨论它是如何工作的。
**例:1#**

```scala
// Scala program to convert Java set 
// to Sequence in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set in Java
        val set = new java.util.HashSet[Int]()

        // Adding integers to the set
        set.add(9)
        set.add(10)
        set.add(11)

        // Converting set to Sequence 
        val seq = set.toSeq

        // Displays Sequence 
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(9, 10, 11)

```

因此，返回一个整数序列。这里，首先创建一个集合，利用 *add* 方法向其中添加整数元素。之后，使用*至*方法将所述集合转换为序列。
**例:2#**

```scala
// Scala program to convert Java set 
// to a Sequence in Scala

// Importing Scala's JavaConversions object
import scala.collection.JavaConversions._

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating set in Java
        val set = new java.util.HashSet[Int]()

        // Adding Integers to the set
        set.add(2)
        set.add(1)
        set.add(3)

        // Converting set to a Sequence
        val seq = set.toSeq

        // Displays Sequence
        println(seq)

    }
}
```

**Output:**

```scala
ArrayBuffer(1, 2, 3)

```

它与上面的例子相同，但是这里集合的元素没有以适当的顺序出现。但是返回的顺序是正确的。