# 从 Java 集到 Scala 集的转换

> 原文:[https://www . geesforgeks . org/conversion-从-a-java-set 到-a-scala-set/](https://www.geeksforgeeks.org/conversion-from-a-java-set-to-a-scala-set/)

通过导入*方法，可以将一个 Java 集合转换为 Scala 集合。在这里，我们需要调用**作为调用集**方法，该方法有一个 java Set 作为参数。因此，该方法返回一个 Scala 集。
现在，让我们来看一些例子。
**例:1#***

```scala
// Scala program of converting a Java Set
// to a Scala Set

// Importing JavaConversions.asScalaSet
import scala.collection.JavaConversions.asScalaSet

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Java List
        val jlist = java.util.Arrays.asList(14, 15, 16)

        // Creating a java Set
        val jSet = new java.util.HashSet[Int]()

        // Adding all the elements of the
        // list to the set
        val x = jSet.addAll(jlist)

        // Converting from java Set
        // to Scala Set
        val results = asScalaSet(jSet)

        // Displays results
        println(results)
    }
}
```

**Output:**

```scala
Set(14, 15, 16)

```

这里返回了一个 Scala 集。在上面的例子中，首先我们创建了一个 Java 列表，然后我们声明了一个 Java 集合 Where，我们使用 **addAll** 方法将 Java 列表的所有元素添加到 Java 集合中。之后，所述的 Java 集合利用**作为标量集合**方法被转换成标量集合。
让我们再看一个例子。
**例:2#**

```scala
// Scala program of converting a Java list
// to a Scala Buffer

// Importing JavaConversions.asScalaSet
import scala.collection.JavaConversions.asScalaSet

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a Java List
        val jlist = java.util.Arrays.asList(11, 9, 5)

        // Creating a java Set
        val jSet = new java.util.HashSet[Int]()

        // Adding all the elements of the
        // list to the set
        val x = jSet.addAll(jlist)

        // Converting from java Set
        // to Scala Set
        val results = asScalaSet(jSet)

        // Displays results
        println(results)
    }
}
```

**Output:**

```scala
Set(5, 9, 11)

```

因此，这里也返回一个集合。此外，这里陈述的列表是以适当的顺序给出的，但是集合需要以适当的顺序给出，因此作为输出返回的集合是以适当的顺序给出的。