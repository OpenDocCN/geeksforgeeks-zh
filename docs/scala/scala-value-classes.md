# Scala |值类

> 原文:[https://www.geeksforgeeks.org/scala-value-classes/](https://www.geeksforgeeks.org/scala-value-classes/)

**值类**是一种新的机制，有助于避免分配运行时对象。**任意值**定义值类。值类是预定义的，它们与类似 Java 的原始语言相一致。
有九种预定义的值类型:Double、Float、Long、Int、Short、Byte、Char、Unit 和布尔值。

**`equals`** 或 **`hashCode`** 不能由一个值类重新定义。值类主要用于优化性能和内存。

让我们用一些例子来理解价值类。

**示例#1:**

```scala
// Scala program to illustrate value class

// Creating a value class and extend with AnyVal
case class C(val name: String) extends AnyVal

// Creating object
object gfg
{
    // Main method
    def main (args: Array[String])
    {
        // Creating the instance of the ValueClass
        val c = new C("GeeksForGeeks")
        c match 
        {   
            // new C instantiated here
            case C("GeeksForGeeks") => println("Matched with GeeksForGeeks")
            case C(x) => println("Not matched with GeeksForGeeks")
        }
    }
}
```

**输出:**

```scala
Matched with GeeksForGeeks
```

在上面的代码中，一个值类借助于 case 类来定义，这里 AnyVal 定义值类(C)。值类由一个字符串参数组成。当我们传递与 case 语句相同的字符串时，这将返回 true，否则返回 false。

**例 2:**

```scala
// Scala program to illustrate value class

// Creating a value class and extend with AnyVal
class Vclass(val a: Int) extends AnyVal 
{
    // Defining method
    def square() = a*a
}

// Creating object
object gfg
{
    // Main method
    def main (args: Array[String])
    {
        // creating the instance of the ValueClass
        val v = new Vclass(5)
        println(v.square())
    }
}
```

**输出:**

```scala
25
```

正如我们可以看到的，在上面的例子中，一个被创建和表示的价值类是一个 **int** 。上述代码由值类`Vclass`中的 *def* 组成。这里 `**Vclass**`是一个用户定义的值类，它包装了 Int 参数并封装了一个 square 方法。要调用 square 方法，请创建 Vclass 类的对象，如下所示: *`val v = new Vclass(5)`*

### 价值类别的一些限制–

*   值类可能没有专门的类型参数。可能没有专门的类型参数。
*   值类可能没有嵌套或局部类、特征或对象。
*   `equals`或`hashCode`不能通过值类重新定义。
*   值类不能有惰性 val、vars 或 val 作为成员。它只能有 defs 作为成员。
*   没有其他类可以扩展值类。