# 在 Scala 中将 Java 字符集转换为序列的程序

> 原文：[https://www.geeksforgeeks.org/program-to-convert-java-set-of-characters-to-sequence-in-scala/](https://www.geeksforgeeks.org/program-to-convert-java-set-of-characters-to-sequence-in-scala/)

利用 Scala 中 Java 的 `toSeq` 方法，可以将一组 Java 字符转换为 Scala 中的序列。在这里，我们需要导入 Scala 的 `JavaConversions` 对象，以便使转换工作。
现在，让我们看一些例子，然后详细讨论它是如何工作的。

## 示例 1

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

// Creating set of character in Java
        val set = new java.util.HashSet[Char]()

// Adding characters to the set
        set.add('a')
        set.add('b')
        set.add('c')

// Converting set to Sequence
        val seq = set.toSeq

// Displays Sequence
        println(seq)

}
}
```

**输出：**

```scala
ArrayBuffer(a, b, c)
```

## 示例 2

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

// Creating set of character in Java
        val set = new java.util.HashSet[Char]()

// Adding characters to the set
        set.add('d')
        set.add('b')
        set.add('c')

// Converting set to Sequence
        val seq = set.toSeq

// Displays Sequence
        println(seq)

}
}
```

**输出：**

```scala
ArrayBuffer(b, c, d)
```