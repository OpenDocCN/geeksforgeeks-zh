# 在 Scala 中打印 Java Set 的程序

> 原文:[https://www . geesforgeks . org/program-to-print-Java-set-in-Scala/](https://www.geeksforgeeks.org/program-to-print-java-set-in-scala/)

通过在 Scala 中编写一个用户定义的 java 方法，可以从 Scala 程序中返回一个 Java 集合。在这里，我们甚至不需要导入任何 Scala 的 *JavaConversions* 对象来进行转换。
现在，让我们来看一些例子。
**例:1#**

```scala
// Scala program to print Java Set 
// in Scala

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

    // Creating a java method in Scala
    def res = {

            // Creating a java Set
            val set = new java.util.HashSet[Int]()

            // Adding elements to the Set
            set.add(6)
            set.add(5)

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
[5, 6]

```

因此，从 Java 方法返回一个集合。在这里，我们不需要导入 Scala 的任何对象。在上面的程序中，一个 Java 方法是用 Scala 程序编写的。其中，该方法将集合的元素一个接一个地添加到所述集合中，然后打印结果。
**例:2#**

```scala
// Scala program to print Java Set 
// in Scala

// Creating object
object GfG
{ 

// Main method
def main(args:Array[String])
{

    // Creating a java method in Scala
    def res = {

            // Creating a java Set
            val set = new java.util.HashSet[Int]()

            // Adding elements to the Set
            set.add(6)
            set.add(5)
            set.add(2)

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
[2, 5, 6]

```

它与上面的例子相同，但是这里在所述集合中增加了一个元素，并且因为它是集合，所以元素的顺序被保持。