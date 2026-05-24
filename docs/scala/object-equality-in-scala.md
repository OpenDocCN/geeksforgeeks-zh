# Scala 中的对象相等

> 原文:[https://www.geeksforgeeks.org/object-equality-in-scala/](https://www.geeksforgeeks.org/object-equality-in-scala/)

在编程语言中，比较两个相等的值是普遍存在的。我们为 Scala 类定义了一个 equals 方法，这样我们就可以相互比较对象实例。在 Scala 中，相等方法表示对象的同一性，然而，它并没有被广泛使用。
在 scala 中，**有三种**不同的等式方法可用–

*   等于方法
*   ==和！=方法
*   ne 和 eq 方法

**注意:** *eq* 的行为与 *==* 运算符在 Java、C++和 C#中的行为相同，但在 Ruby 中不==。 *ne* 法是对 eq 的*否定，即相当于*！(x eq y)* 。在 Java、C++和 C#中， *==* 运算符测试是为了参考，而不是值相等。相比之下，Ruby 的 *==* 运算符测试值是否相等。但是在 Scala 中， *==* 正在测试值相等。
我们举个例子来了解一下。
**例:***

## 斯卡拉

```scala
// Scala program of Equals

// Creating a case class of
// Subject
case class Subject (LanguageName:String, TopicName:String)

// Creating object
object GFG
{
    // Main method
    def main(args: Array[String])
    {
        // Creating objects
        var x = Subject("Scala", "Equality")
        var y = Subject("Scala", "Equality")
        var z = Subject("Java", "Array")

        // Displays true if instances
        // are equal else false
        println(x.equals(y))
        println(x.equals(z))
        println(y == z)

    }
}
```

**输出:**

```scala
true
false
false
```

*   **equals 方法:**用于测试值相等性的 equals 方法。如果 x 和 y 具有相同的值，则 x 等于 y 为真。它们不需要引用相同的实例。因此，Java 中的 equals 方法和 Scala 中的 equals 方法行为相同。
*   **The == and！= Methods:** 虽然==是几种语言中的运算符，但是 Scala 为每种类型的自然等式保留了==等式。这是 Scala 中的一个方法，在 Any 中定义为 final。价值平等将由此得到检验。这里，如果 x 和 y 具有相同的值，则 x == y 为真。
*   **ne 和 eq 方法:**参考等式将通过 eq 方法进行测试。这里，如果 x 和 y 都指向内存中的同一个位置，或者 x 和 y 引用同一个对象，则 x eq y 为真。这些方法只为 AnyRef 定义。

如果两个对象根据 equals 方法是相等的，那么对两个对象中的每一个调用 hash code 方法必须产生相同的整数结果。默认情况下，equals (and，==)与 eq 相同，但是我们可以通过在定义的类中重写 equals 方法来更改它的行为。Scala 对待==就像在 Any 类中定义的一样:
下面是 equals 方法和相应 hashCode 方法的示例:
**示例:**

## 斯卡拉

```scala
// Scala program to illustrate how
// hashCode() and equals() methods work

// Creating class
class Subject (name: String, article: Int)
{
    // Defining canEqual method
    def canEqual(a: Any) = a.isInstanceOf[Subject]

    // Defining equals method with override keyword
    override def equals(that: Any): Boolean =
        that match
    {
        case that: Subject => that.canEqual(this) &&
                    this.hashCode == that.hashCode
        case _ => false
    }

    // Defining hashcode method
    override def hashCode: Int = {
        val prime = 31
        var result = 1
        result = prime * result + article;
        result = prime * result +
                (if (name == null) 0 else name.hashCode)
        return result
    }
}

// Driver code
object GFG
{
    // Main method
    def main(args: Array[String])
    {

        // Creating the Objects of Geek class.
        // Subject g1 = new Subject("aa", 1);
        val g1 = new Subject("Scala", 28)
        val g2 = new Subject("Scala", 28);

        // Comparing above created Objects.
        if(g1.hashCode() == g2.hashCode())
        {

            if(g1.equals(g2))
                println("Both Objects are equal. ");
            else
                println("Both Objects are not equal. ");

        }
        else
            println("Both Objects are not equal. ");
    }
}
```

**输出:**

```scala
Both Objects are equal. 
```

在上面的例子中，Eclipse 为一个类似的 Java 类生成了一个 hashCode 方法的修改版本。它还使用 canEqual 方法。定义了 equals 方法后，我们可以用==，来比较**主题**的实例。