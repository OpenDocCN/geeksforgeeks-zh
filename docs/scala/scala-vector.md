# 标量–矢量

> 原文:[https://www.geeksforgeeks.org/scala-vector/](https://www.geeksforgeeks.org/scala-vector/)

[Scala](https://www.geeksforgeeks.org/scala-programming-language/) 是一种面向对象的编程语言，支持函数式和多范式。Scala 生成字节代码并在 [Java 虚拟机](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/)上运行。**Scala 中的向量**是不可变的数据结构，为元素提供随机访问，类似于列表。但是，该列表具有随机访问元素的无能。下面是在 Scala 中对向量执行的一些操作的实现:

**1。创建向量:**可以在 Scala 中使用 vector()函数创建一个新向量，并提供括号中的元素。

*例:*

## 斯卡拉

```scala
import scala.collection.immutable._
object GFG {

    def main(args: Array[String]){

        // Creating vector
        var vector1 = Vector(2, 3, 4, 5)

        // Using println and foreach function
        // To print elements of vector
        println(vector1)
        vector1.foreach((element:Int) => print(element+" "))
    }
}
```

**Output:**

```scala
Vector(2, 3, 4, 5)
2 3 4 5 
```

**2。向向量中添加元素:**可以使用 **:+** 运算符在 Scala 中向向量中添加单个元素，可以使用**+**运算符在向量中添加多个元素。

*例:*

## 斯卡拉

```scala
import scala.collection.immutable._
object GFG {

    def main(args: Array[String]){

        // Creating vector
        var vector1 = Vector(2, 3, 4, 5)

        // Adding new elements into new vector
        var newVector = vector1 :+ 10
        print("\nVector Elements after adding: ")
        newVector.foreach((element:Int) => print(element+" "))

        // Creating vector
        var vector2 = Vector(7, 100)

        // Merging two vectors
        var mergeVector = newVector ++ vector2
        print("\nVector Elements after merging: ")
        mergeVector.foreach((element:Int) => print(element+" "))
    }
}
```

**Output:**

```scala
Vector Elements after adding: 2 3 4 5 10 
Vector Elements after merging: 2 3 4 5 10 7 100 
```

**3。反转向量元素:**向量的元素可以使用 scala.collection .不可变包中的反转函数按照插入的顺序反转。

*例:*

## 斯卡拉

```scala
import scala.collection.immutable._
object GFG {

    def main(args: Array[String]){

        // Creating vector
        var vector1 = Vector(2, 3, 4, 5)
        print("\nVector elements before reversing: ")
        vector1.foreach((element:Int) => print(element+" "))

        // Reverse vector elements
        var rev = vector1.reverse
        print("\nVector Elements after reversing: ")
        rev.foreach((element:Int) => print(element+" "))
    }
}
```

**Output:**

```scala
Vector elements before reversing: 2 3 4 5 
Vector Elements after reversing: 5 4 3 2 
```

**4。向量元素排序:**向量的元素可以使用 Scala 中的排序函数进行排序。

*例:*

## 斯卡拉

```scala
import scala.collection.immutable._
object GFG {

    def main(args: Array[String]){

        // Creating vector
        var vector1 = Vector(5, 1, 9, 100, 2, 25, 17)
        print("\nVector elements before sorting:")
        vector1.foreach((element:Int) => print(element+" "))

        // Sorting vector elements
        var st = vector1.sorted

        print("\nVector Elements after sorting: ")
        st.foreach((element:Int) => print(element+" "))
    }
}
```

**Output:**

```scala
Vector elements before sorting:5 1 9 100 2 25 17 
Vector Elements after sorting: 1 2 5 9 17 25 100 
```