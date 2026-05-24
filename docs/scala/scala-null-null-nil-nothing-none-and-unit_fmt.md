# Scala 中的 Null、null、Nil、Nothing、None 和 Unit

> 原文：[https://www.geeksforgeeks.org/scala-null-null-nil-nothing-none-and-unit/](https://www.geeksforgeeks.org/scala-null-null-nil-nothing-none-and-unit/)

Scala 中的空值由 `Null`、`null`、`Nil`、`Nothing`、`None` 和 `Unit` 表示。这些空值的解释如下：

## null

`Objects`、`Strings` 等引用类型可以是 `null`，`Int`、`Double`、`Long` 等值类型不能是 `null`。Scala 中的 `null` 类似于 Java 中的 `null`。

## Null

`Null` 是一个特质（Trait），它是所有引用类型的子类型，但完全不是值类型的子类型。`Null` 的唯一实例是 `null`。引用类型可以被赋值为 `null`，但值类型不能。

**示例：**

```scala
// Scala program using Null and null

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Method that takes a parameter of type Null
        def usingnull(thing: Null): Unit =
        {
            println("GeeksForGeeks");
        }

        /*error: type mismatch;
        found   : java.lang.String("hey")
        required: Null*/
        //usingnull("hey")

        // passing null itself
        usingnull(null)
    }
}
```

**输出：**

```scala
GeeksForGeeks
```

这里，方法 `usingnull` 接受一个类型为 `Null` 的参数，我们只能传递两件事：`null` 本身或 `Null` 类型的引用。当我们传递一个字符串作为参数时，它不起作用并产生了一个错误。

## Nothing

`Nothing` 也是一个特质，没有实例。它是所有类型的子类型。这个特质的主要动机是为那些总是抛出异常的方法提供一个返回类型，也就是说，这些方法通常甚至不会返回。它也有助于提供 `Nothing` 的类型。

## Unit

Scala 中的 `Unit` 类似于 Java 中的 `void`，当函数不返回任何内容时，它被用作该函数的返回类型。

**示例：**

```scala
// Scala program using Unit type

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Method return type is unit
        def printNumber(num: (Int) => Unit) =
        {
            num(1);
            num(2);
            num(3);
        }

        printNumber(println)
    }
}
```

**输出：**

```scala

```

这里，方法 `printNumber` 接受一个名为 `num` 的参数，其类型为 `(Int) => Unit`。这意味着 `num` 是一个接受 `Int` 类型单个参数的方法。方法 `printNumber` 返回 `Unit` 类型，也就是说 `num` 不应该返回值。

## Nil

`Nil` 被认为是一个包含零个元素的列表。`Nil` 的类型是 `List[Nothing]`，如上所述，`Nothing` 没有实例，因此我们可以拥有一个被确认为空的列表。

**示例：**

```scala
// Scala program to show that
// Nil is an empty list

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Displays empty list
        println(Nil)
    }
}
```

**输出：**

```scala
List()
```

因此，我们可以看到返回了一个空列表。

## None

`None` 是 Scala 的 `Option` 类的子类之一，用于避免将 `null` 赋值给引用类型。让我们看一些例子。

**示例：**

```scala
// Scala program to convert
// None to empty list

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Displays empty list
        println(None.toList)
    }
}
```

**输出：**

```scala
List()
```

这里，返回一个空列表。

**示例：**

```scala
// Scala program to test if
// None is empty or not

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Displays true if empty
        // else false
        println(None.isEmpty)
    }
}
```

**输出：**

```scala
true
```

因此，我们可以说 `None` 为空，返回 `true`。

**示例：**

```scala
// Scala program to convert None
// to String

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Displays String
        println(None.toString)
    }
}
```

**输出：**

```scala
None
```

因此，`None` 可以转换成字符串。

**示例：**

```scala
// Scala program of utilizing
// None with Scala's Option

// Creating object
object GfG
{
    // Main method
    def main(args: Array[String])
    {
        // Applying None with
        // Scala's Option
        val p: Option[String] = None

        // Displays output
        println(p)
    }
}
```

**输出：**

```scala
None
```

有关该示例的更多信息，请参见 [Scala 的 Option](https://www.geeksforgeeks.org/scala-option/)。