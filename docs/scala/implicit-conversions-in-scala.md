# Scala 中的隐式转换

> 原文:[https://www . geeksforgeeks . org/implicit-conversions-in-Scala/](https://www.geeksforgeeks.org/implicit-conversions-in-scala/)

**Scala 中的隐式转换**是在使用错误类型的对象时应用的一组方法。它允许编译器自动将一种类型转换成另一种类型。
隐式转换适用于两种情况:

*   首先，如果 A 和 S 类型的表达式与预期的 b 类型表达式不匹配
*   第二，在类型 A 的表达式 e 的选择 e.m 中，如果选择器 m 不代表 A 的成员

在第一个条件中，搜索一个适合于表达式并且其结果类型匹配于 b 的转换。在第二个条件中，搜索一个适合于表达式并且其结果携带名为 m.
的成员的转换。现在，让我们用一个例子来理解。
对列表[Int]类型的两个列表 xa 和 ya 的以下操作是合法的:

```scala
 xa = ya
```

假设隐式方法 listorder 和 intorder 在下面的作用域中定义:

> 隐式 def listorder[A](x: List[A])
> (隐式 elemorder:A =>Ordered[A]):Ordered[List[A]]=
> 新的 Ordered[List[A]] { /*..*/ }
> 隐式 def intoorder(x:Int):Ordered[Int]=
> new Ordered[Int]{/*..*/ }

让我们看一个例子。
**例:**

## 斯卡拉

```scala
// Scala program of implicit conversions
import A.fromString
import scala.language.implicitConversions

case class A(s: String)
object A
{
    // Using implicitConversions   
    implicit def fromString(s: String): A = A(s)
}

class C
{
  def m1(a: A) = println(a)
  def m(s: String) = m1(s)
}

// Creating object
object C
{
    // Main method
    def main(args: Array[String])
    {
        var b : A = ("GeeksforGeeks")
         println(b)

    }
}
```

**输出:**

```scala
A(GeeksforGeeks)
```

隐式转换有一个缺点，如果它是随机使用的，编译器会在编译隐式转换定义时发出警告。
为了避免警告，我们需要采取这两个步骤中的任何一个:

*   将 Scala . language . implicit conversions 导入隐式转换定义的范围。
*   用-language:Implicitations 调用编译器。

现在，让我们看另一个例子。
**例:**

## 斯卡拉

```scala
// Scala program of implicit conversions
import ComplexImplicits._

object ComplexImplicits
{
    // implicit conversion
    implicit def DoubleComplex(value : Double) =
                        new Complex(value,0.0)

    implicit def TupleComplex(value : Tuple2[Double,Double]) =
                        new Complex(value._1,value._2);

}

// Creating a class containg different method
class Complex(val r : Double, val i : Double)
{

    def +(that: Complex) : Complex =
    (this.r + that.r, this.i + that.i)

    def -(that: Complex) : Complex =
    (this.r - that.r, this.i + that.i)

    def unary_~ = Math.sqrt(r * r + i * i)

    override def toString = r + " + " + i + "i"

}

// Creating Object
object Complex
{

val i = new Complex(0,1);

// Main method   
def main(args : Array[String]) : Unit =
{
    var a : Complex = (6.0,4.0)
    var b : Complex = (1.0,2.0)
    println(a)
    println(a + b)
    println(a - b)
    println(~b)

    var c = 5 + b
    println(c)
    var d = (3.0,3.0) + c
    println(d)
}
}
```

**输出:**

```scala
6.0 + 4.0i
7.0 + 6.0i
5.0 + 6.0i
2.23606797749979
6.0 + 2.0i
9.0 + 5.0i
```