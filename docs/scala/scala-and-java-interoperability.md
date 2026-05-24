# Scala 和 Java 互操作性

> 原文:[https://www . geesforgeks . org/Scala-and-Java-互操作性/](https://www.geeksforgeeks.org/scala-and-java-interoperability/)

Java 是最顶尖的编程语言之一，而 **JVM** (Java 虚拟机)工具使其更容易在其中开发。但是 Java 中有一些小的调整和特性，所以开发人员会像 Scala 一样寻找不同的选项。 **Scala 和 Java 的互操作性**意味着用一种语言编写的代码可以很容易地在另一种语言中执行，只需做一些修改。

考虑到 Scala 的好处，比如功能特性(少写多工作)、内置数据结构、强大的继承性，以及最重要的 JVM 支持，它已经被证明是一种有效的编程语言。

下面显示了一个将 Java 代码转换成 Scala 可读代码的例子。使用数组列表的一个例子如下:

```scala
// Java program to create and print ArrayList.
import java.util.ArrayList;
import java.util.List;

public class CreateArrayList
{
    public static void main(String[] args)
    {
        List<String> students = new ArrayList<>();
        students.add("Raam");
        students.add("Shyaam");
        students.add("Raju");
        students.add("Rajat");
        students.add("Shiv");
        students.add("Priti");

        //Printing an ArrayList.
        for (String student : students) 
        {
            System.out.println(student);
        }
    }
}
```

**输出:**

```scala
Raam
Shyaam
Raju
Rajat
Shiv
Priti

```

一旦 Scala REPL 启动，Java 标准库就可以使用了。有时需要在 Scala 代码中添加 Java 集合。同样的代码可以用 Scala 编写，如下所示:

```scala
// Scala conversion of the above program.
import java.util.ArrayList;
import scala.collection.JavaConversions._

// Creating object
object geeks
{
    // Main method
    def main(args: Array[String])  
    {
        val students = new ArrayList[String]

        students.add("Raam");
        students.add("Shyaam");
        students.add("Raju");
        students.add("Rajat");
        students.add("Shiv");
        students.add("Priti");

        // Printing the ArrayList
        for (student <- students) 
        {
            println(student)
        }
    }
}
```

**输出:**

```scala
Raam
Shyaam
Raju
Rajat
Shiv
Priti

```

然而，有一些 Scala 特性和集合缺乏 Java 等效性。Java 和 Scala 集合之间的主要区别通常被认为是 Scala 可遍历性不是 Java 可迭代性，反之亦然。但是，使用一些命令可以进行转换。有时，一个人需要将自己的集合传递给另一个人的代码。为了实现这一点，在 Scala 代码中添加了以下命令:

```scala
scala> import collection.JavaConverters._
import collection.JavaConverters._ 
```

以下示例显示了 Java 集合到 Scala 的转换，反之亦然。**。asJava** 和**。asScala** 是支持上述转换的扩展功能。

*   **将 Scala 集合转换为 Java** :

    ```scala
    import scala.collection.JavaConverters._

    val listInScala = List(10, 20, 30)
    JavaLibrary.process(listInScala.asJava)
    ```

*   **To convert the Java collections to Scala**:

    ```scala
    import scala.collection.JavaConverters._

    val JavaCol= JavaLibrary.getList
    val ScalaCol= JavaCol.asScala
    ```

    Scala 集合可以使用 *scala.collection* 合并，子集合可以使用`scala.collection.mutable`和`scala.collection.immutable`合并。一个**可变的**集合可以改变，但是一个**不可变的**集合不能改变。然而，仍然可以对集合运行诸如加法之类的操作，但是它只会给出一个新的集合，而保持旧的集合不变。

    显示相同情况的示例如下:

    ```scala
    // Java Program to return a HashMap.
    import java.util.HashMap;
    import scala.collection.JavaConverters;
    import scala.Predef;
    import scala.Tuple2;
    import scala.collection.immutable.Map;

    public class ConvertToScala 
    {
        public static <A, B> Map<A, B> MapInScala(HashMap<A, B> exampleMap)
        {
            return JavaConverters.mapAsScalaMapConverter(exampleMap).
                    asScala().toMap(Predef.<Tuple2<A, B> >conforms());
        }

        public static HashMap<String, String> Example()
        {
            HashMap<String, String> exampleMap = new HashMap<String, String>();
            exampleMap.put("Ayush", "Boy");
            exampleMap.put("Ridhi", "Girl");
            exampleMap.put("Soumya", "Girl");
            return exampleMap;
        }
    }
    ```

    The above code can be converted in Scala as follows:

    上述程序的 Scala 版本。

    > Scala > val javamap:Java . util . hashmap[String，String] = ConvertToScala。示例
    > javamap:Java . util . hashmap[String，String] = {Ridhi=Girl，Soumya=Girl，Ayush=Boy}
    > 
    > scala> val scalamap: Map[String，String] = ConvertToScala。MapInScala(javamap)
    > Scala Map:Map[String，String] = Map(Ridhi - > Girl，Soumya - > Girl，Ayush - > Boy)

    总之，Java 和 Scala 互操作性要求将 Scala 的一些集合分配给 Java 代码，反之亦然。尽管如此，考虑到编写代码的字符数量较少，用 Scala 编程并不乏味，而且比用 Java 编程更好。此外，这两个代码的转换使得开发人员更容易获得 Scala 的支持。

    ________________________________________________________________________________________