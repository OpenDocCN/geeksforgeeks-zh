# Scala 中的枚举

> 原文:[https://www.geeksforgeeks.org/enumeration-in-scala/](https://www.geeksforgeeks.org/enumeration-in-scala/)

枚举用于在编程语言中表示一组命名常数。有关枚举的信息，请参考 C 语言中的[枚举(或枚举)](https://www.geeksforgeeks.org/enumeration-enum-c/)和 Java 语言中的[枚举](https://www.geeksforgeeks.org/enum-in-java/)。Scala 提供了一个**枚举**类，我们可以扩展它来创建我们的枚举。
**Scala 中枚举的声明**

## 斯卡拉

```scala
// A simple scala program of enumeration

// Creating enumeration
object Main extends Enumeration
{
    type Main = Value

    // Assigning values
    val first = Value("Thriller")
    val second = Value("Horror")
    val third = Value("Comedy")
    val fourth = Value("Romance")

    // Main method
    def main(args: Array[String])
    {
        println(s"Main Movie Genres = ${Main.values}")
    }
}
```

**Output:** 

```scala
Main Movie Genres = Movies.ValueSet(Thriller, Horror, Comedy, Romance)
```

**重要的枚举点:**

*   在 Scala 中，没有像 Java 或 C 那样的枚举关键字。
*   Scala 提供了一个枚举类，我们可以扩展它来创建我们的枚举。
*   每个枚举常数代表一个枚举类型的**对象**。
*   枚举值被定义为评估的**值**成员。
*   当我们扩展枚举类时，很多函数被继承。身份证就是其中之一。
*   我们可以迭代成员。

**打印特定元素的枚举**

## 斯卡拉

```scala
// Scala program Printing particular
// element of the enumeration

// Creating enumeration
object Main extends Enumeration
{
    type Main = Value

    // Assigning values
    val first = Value("Thriller")
    val second = Value("Horror")
    val third = Value("Comedy")
    val fourth = Value("Romance")

    // Main method
    def main(args: Array[String])
    {
        println(s"The third value = ${Main.third}")
    }
}
```

**Output:** 

```scala
The third value = Comedy
```