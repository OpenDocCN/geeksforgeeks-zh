# 在 Scala 中打印 Java 字符集的程序

> 原文:[https://www . geesforgeks . org/program-to-print-Java-字符集-in-scala/](https://www.geeksforgeeks.org/program-to-print-java-set-of-characters-in-scala/)

通过在 Scala 中编写用户定义的 java 方法，可以从 Scala 程序中返回一组 Java 字符。在这里，我们甚至不需要导入任何 Scala 的 *JavaConversions* 对象来进行转换。
现在，让我们来看一些例子。
**例:1#**

```scala
// Scala program to print Java Set 
// of characters in Scala

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a java method in Scala
        def res = {

                // Creating a java Set of characters 
                val set = new java.util.HashSet[Char]()

                // Adding characters to the Set 
                set.add('a')
                set.add('b')
                set.add('c')

                    // Displays output
                    println(set)
                                }

        // Assigning result method to set of characters
        val set = res
    }
}
```

**Output:**

```scala
[a, b, c]

```

因此，从 Java 方法返回一组字符。在这里，我们不需要导入 Scala 的任何对象。在上面的程序中，一个 Java 方法是用 Scala 程序编写的。其中，该方法将字符元素一个接一个地添加到所述集合中，然后打印结果。
**例:2#**

```scala
// Scala program to print Java Set 
// of characters in Scala

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a java method in Scala
        def res = {

                // Creating a java Set of characters 
                val set = new java.util.HashSet[Char]()

                // Adding characters to the Set
                set.add('j')
                set.add('l')
                set.add('k')

                    // Displays output
                    println(set)
                                }

        // Assigning result method to set
        val set = res
    }
}
```

**Output:**

```scala
[j, k, l]

```

它与上面的例子相同，但是这里在所述的字符集中增加了一个元素，因为它是一个集合，所以元素的顺序保持不变。