# Scala 中性状和抽象类的区别

> 原文:[https://www . geeksforgeeks . org/Scala 中特征类和抽象类的区别/](https://www.geeksforgeeks.org/difference-between-traits-and-abstract-classes-in-scala/)

在 Scala 中，[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-scala/)是使用抽象关键字构造的。它包含抽象和非抽象方法，并且不能支持多重继承。
T3】例:

```scala
// Scala program to illustrate how to 
// create an abstract class

// Abstract class
abstract class Abstclass
{

    // Abstract and non-abstract method
    def portal
    def tutorial()
    { 
        println("Scala tutorial")
    }

}

// GFG class extends abstract class
class GFG extends Abstclass
{
    def portal()
    {
        println("Welcome!! GeeksforGeeks")
    }
}

object Main 
{

    // Main method
    def main(args: Array[String]) 
    {
        // object of GFG class
        var obj = new GFG ();
        obj.tutorial()
        obj.portal()
    }
}
```

**输出:**

```scala
Scala tutorial
Welcome!! GeeksforGeeks

```

像类一样，**特征**可以有方法(抽象的和非抽象的)和字段作为其成员。特性就像 Java 中的接口。但是它们比 Java 中的接口更强大，因为在特性上我们被允许实现成员。
T3】例:

```scala
// Scala program to illustrate how to 
// create traits

// traits
trait mytrait
{

    // Abstract and non-abstract method
    def portal
    def tutorial()
    { 
        println("Scala tutorial")
    }

}

// GFG class extends trait
class GFG extends mytrait
{
    def portal()
    {
        println("Welcome!! GeeksforGeeks")
    }
}

object Main 
{

    // Main method
    def main(args: Array[String]) 
    {

        // object of GFG class
        var obj = new GFG ();
        obj.tutorial()
        obj.portal()
    }
}
```

**输出:**

```scala
Scala tutorial
Welcome!! GeeksforGeeks

```

| 特征 | 抽象类 |
| 性状支持多重遗传。 | 抽象类不支持多重继承。 |
| 我们可以给一个对象实例添加一个特性。 | 我们不允许向对象实例添加抽象类。 |
| Traits 不包含构造函数参数。 | 抽象类包含构造函数参数。 |
| 只有当特征不包含任何实现代码时，它们才是完全可互操作的。 | 抽象类完全可以与 Java 代码互操作。 |
| 特质是可以叠加的。所以，超级调用是动态绑定的。 | 抽象类是不可堆叠的。所以，超级调用是静态绑定的。 |