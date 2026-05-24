# 在 Scala 中打印 Java 字符串列表的程序

> 原文:[https://www . geesforgeks . org/program-to-print-Java-list-in-string-Scala/](https://www.geeksforgeeks.org/program-to-print-java-list-of-strings-in-scala/)

通过在 Scala 中编写一个用户定义的 java 方法，可以从 Scala 程序中返回一个 Java 字符串列表。在这里，您甚至不需要导入任何 Scala 的 *JavaConversions* 对象来进行转换。
现在，让我们来看一些例子。
**例:1#**

```scala
// Scala program to print Java List 
// of strings in Scala

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

    // Creating a java method in Scala
    def result = {

        // Creating a java list of strings
        val list = new java.util.ArrayList[String]()

        // Adding string elements in the List
        list.add("gfg")
           list.add("cs")

           // Displays output
           println(list)    }

    // Assigning result method to list
    val list = result
}
}
```

**Output:**

```scala
[gfg, cs]

```

因此，从一个 Java 方法返回一个字符串列表。在这里，您不需要导入 Scala 的任何对象。在上面的程序中，一个 Java 方法是用 Scala 程序编写的。其中，此方法将列表的字符串元素一个接一个地添加到指定的列表中，然后打印结果。
**例:2#**

```scala
// Scala program to print Java List 
// of strings in Scala

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

    // Creating a java method in Scala
    def result = {

        // Creating a java list of strings
        val list = new java.util.ArrayList[String]()

        // Adding string elements in the List
        list.add("Nidhi")
        list.add("is an")
        list.add("author")

        // Displays output
        println(list) }

    // Assigning result method to list
    val list = result
}
}
```

**Output:**

```scala
[Nidhi, is an, author]

```

它与上面的例子相同，但是这里在所述列表中增加了一个元素，并且这里不需要元素的正确顺序。