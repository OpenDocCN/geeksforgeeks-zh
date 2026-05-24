# 标量–协方差

> 原文:[https://www.geeksforgeeks.org/scala-covariance/](https://www.geeksforgeeks.org/scala-covariance/)

差异是复杂类型或其组成类型的子类型关系的相互联系。Scala 提供了三种类型的差异:

*   协变的
*   逆变的
*   不变的

**协方差**表示如果有两个参数化的类型，S 是 T 的一个子类型，那么 List[S]就是 List[T]的一个子类型。这是一种继承关系。所以，这基本上定义了我们能否用一个类型的基类型来替换它的关系。简单地说，如果我们举一个例子，汽车是车辆的一个子类型，那么列表[汽车]就是列表[车辆]的一个子类型。所以我们可以用 List[Vehicle]代替 List[Car]。当我们声明一个类型是协变的，那么它在不同位置的安全使用就会受到限制。在不可变类型的情况下，协方差被广泛使用。
**语法:**

```scala
List[+T]
```

这里，T 是一个类型参数，符号“+”代表 Scala 协方差。

让我们借助示例来讨论这个概念:
**示例 1:**

```scala
// Scala program to illustrate the concept of covariance

// Creating an abstract class 
// for Flower 
abstract class Flower 
{
    def name: String
}

// Creating a sub-class Lily 
// of Flower 
case class Lily(name: String) extends Flower

// Creating a sub-class Carnation
// of Flower 
case class Carnation(name: String) extends Flower 
object Covariance extends App
{

    // Creating a method
    def FlowerNames(flowers: List[Flower]): Unit =
    {   
        flowers.foreach 
        {
            flower => println(flower.name)
        }
    }

    // Assigning names
    val lily: List[Lily] = List(Lily("White Lily"), 
                                Lily("Jersey Lily"))
    val carnations: List[Carnation] = List(Carnation("White carnations"),
                                           Carnation("Pink carnations"))

    // Print: names of lily 
    FlowerNames(lily)

    // Print: names of carnation 
    FlowerNames(carnations)
}
```

**输出:**

```scala
White Lily
Jersey Lily
White carnations
Pink carnations

```

**说明:**在上例中，百合和康乃馨是花的亚型。所以，很明显，一个列表[百合]就是一个列表[花]，一个列表[康乃馨]也是一个列表[花]，我们可以用它们中的任何一个来代替一个列表[花]。在代码的后面部分，有一个方法 FlowerNames 打印花的名称，可接受的参数是花的列表。如果这两个列表是协变的，只有这样方法调用才会编译，花名才会分别打印出来。因此，由于百合和康乃馨是花的一个子类型，最后两行将由于协方差而执行。
T3【注:

*   抽象类在这里被用来应用协方差，因为它有列表[+T]，其中类型参数 T 是协变的。
*   这里使用了一个特性应用程序来快速地将对象转换成可用的程序。

**例 2:**

```scala
// Scala program to illustrate the concept of covariance

// Creating an abstract class 
// for Animal
abstract class Animal 
{
    def name: String
}

// Creating a sub-class Mammal
// of Animal 
case class Mammal(name: String) extends Animal

// Creating a sub-class Reptile
// of Animal 
case class Reptile(name: String) extends Animal 

object CovarianceExample extends App
{

    // Creating a method
    def SpecieNames(animals: List[Animal]): Unit =
    {   
        animals.foreach 
        { 
            animal =>println(animal.name)
        }
    }

    // Assigning names
    val mammals: List[Mammal] = List(Mammal("Zebra"), 
                                     Mammal("Horse"))
    val reptiles: List[Reptile] = List(Reptile("Snake"), 
                                       Reptile("Lizard"))

    // Print: names of mammals
    SpecieNames(mammals)

    // Print : names of reptiles
    SpecieNames(reptiles)
}
```

**输出:**

```scala
Zebra
Horse
Snake
Lizard

```