# Scala 中的物体铸造

> 原文:[https://www.geeksforgeeks.org/object-casting-in-scala/](https://www.geeksforgeeks.org/object-casting-in-scala/)

为了将对象(即实例)从一种类型转换为另一种类型，必须使用**作为**方法的实例。这个方法在类*任意*中定义，它是 scala 类层次结构的根(像 Java 中的 Object 类)。方法的 asInstanceOf 属于类*的具体值成员 Any* ，用于铸造接收器对象。

**Applications of asInstanceof method**

*   在应用程序上下文文件中显示 beans 时需要这个视角。
*   它也用于转换数值类型。
*   它甚至可以应用在复杂的代码中，比如与 Java 通信并向它发送一个对象实例数组。

**Examples of casting using asInstanceof method**

*   从整数到浮点的转换。
    **例:**

## 斯卡拉

```scala
// Scala program of Object Casting
// Int to Float
case class Casting(a:Int)

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {
         val a = 10

        // Casting value of a into float
        val b = a.asInstanceOf[Float]

        println("The value of a after" +
        " casting into float is " + b)
    }
}
```

**Output:** 

```scala
The value of a after casting into float is 10.0
```

*   这里，“a”的类型是整数，转换类型后将是浮点型，这是转换数字类型的例子。
*   从字符到整数的转换。
    **例:**

## 斯卡拉

```scala
// Scala program of Object Casting
// Char to Int
case class Casting(c:Char)

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {
         val c = 'c'

        // Casting value of c into Int
        val d = c.asInstanceOf[Int]

        println("The value of c after" +
        " casting into Integer is " + d)
    }
}
```

**Output:** 

```scala
The value of c after casting into Integer is 99
```

*   这里，“c”的类型是字符，转换后的类型将是整数，这给出了“c”的 ASCII 值。
*   从浮点到整数的转换。
    **例:**

## 斯卡拉

```scala
// Scala program of Object Casting
// Float to Int
case class Casting(a:Float, b:Float)

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {
         val a = 20.5
         val b = 10.2

        // Casting value of c into Int
        val c = (a/b).asInstanceOf[Int]

        println("The value of division after" +
        " casting float into Integer will be " + c)
    }
}
```

**Output:** 

```scala
The value of devision after casting float into Integer will be 2
```

*   这里，“a”和“b”的类型是浮动的，但是在铸造之后，类型将是浮动的。