# 在 Scala 中打印 Java 字符列表的程序

> 原文:[https://www . geesforgeks . org/program-to-print-Java-Scala 中的字符列表/](https://www.geeksforgeeks.org/program-to-print-java-list-of-characters-in-scala/)

通过在 Scala 中编写一个用户定义的 java 方法，可以从 Scala 程序中返回一个 Java 字符列表。在这里，我们甚至不需要导入任何 Scala 的 *JavaConversions* 对象来进行转换。
现在，让我们来看一些例子。
**例:1#**

```scala
// Scala program to print Java List 
// of characters in Scala

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a java method in Scala
        def result = {

                // Creating a java list of characters 
                val list = new java.util.ArrayList[Char]()

                // Adding string elements in the List
                list.add('g')
                list.add('f')
                list.add('g')

                    // Displays output
                    println(list)
                                }

        // Assigning result method to list
        val list = result
    }
}
```

**Output:**

```scala
[g, f, g]

```

因此，从一个 Java 方法返回一个字符列表。在这里，我们不需要导入 Scala 的任何对象。在上面的程序中，一个 Java 方法是用 Scala 程序编写的。其中，该方法将列表中的字符元素一个接一个地添加到指定的列表中，然后打印结果。
**例:2#**

```scala
// Scala program to print Java List 
// of characters in Scala

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a java method in Scala
        def result = {

                // Creating a java list of characters 
                val list = new java.util.ArrayList[Char]()

                // Adding string elements in the List
                list.add('l')
                list.add('m')
                list.add('n')

                    // Displays output
                    println(list)
                                }

        // Assigning result method to list
        val list = result
    }
}
```

**Output:**

```scala
[l, m, n]

```

它与上面的例子相同，但是这里在所述列表中增加了一个元素，并且这里不需要元素的正确顺序。