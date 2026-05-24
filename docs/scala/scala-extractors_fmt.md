# Scala 提取器

> 原文: [https://www.geeksforgeeks.org/scala-extractors/](https://www.geeksforgeeks.org/scala-extractors/)

在 Scala 中，提取器被定义为一个对象，该对象有一个名为 `unapply` 的方法。这个方法提取一个对象并返回其属性。这种方法也用于模式匹配和部分函数。提取器还解释了 `apply` 方法，该方法接受参数并构造一个对象，因此有助于构造值。`unapply` 方法与 `apply` 方法的构造过程相反。

**`unapply` 方法的返回类型可以选择如下:**

*   如果是用于检查，则返回一个 `Boolean` 类型。
*   如果该过程只返回一个类型为 `T` 的值，则返回一个 `Option[T]`。
*   如果该过程返回 `T1`、`T2`、…、`Tn` 类型的多个值，则返回可选元组，即 `Option[(T1, T2, …, Tn)]`。
*   如果该过程返回不可预测数量的值，则提取器可以用返回 `Option[Seq[T]]` 的 `unapplySeq` 来定义。

**示例:**

## Scala

```scala
// Scala program of extractors

// Creating object
object Name
{

    // Main method
    def main(args: Array[String])
    {

        // Defining apply method
        def apply(firstname: String, lastname: String) =
        {
            firstname +"kumari"+ lastname

        }

        // Defining unapply method
        def unapply(x: String): Option[(String, String)] =
        {

            // Applying a method split
            val y = x.split("kumari")

            if (y.length == 2)
            {

                Some(y(0), y(1))

            }
            else
                    None

        }

        // Displays output
        println ("The Apply method returns : " +
                        apply("Nidhi", "Singh"))
        println ("The Unapply method returns : " +
                        unapply("NidhikumariSingh"))
    }
}
```

**Output:**

```scala
The Apply method returns : NidhikumariSingh
The Unapply method returns : Some((Nidhi, Singh))
```

这里，这个示例显示了 `Name` 的提取器对象。对象 `Name` 定义了两种方法 `apply` 和 `unapply`。`apply` 方法接受括号中指定的参数，并创建方法中指定的值。名字和姓氏加上中间的 **kumari** (中间名)被返回。`unapply` 方法按照指定的方式分解参数，并将 `firstname` 对象返回到提取器中。如果作为参数传递名字和姓氏，则返回一对字符串，否则不返回任何字符串。

**示例:**

## Scala

```scala
// Scala program of extractors

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Defining apply method
        def apply(q: Double): Double = q * 10

        // Defining unapply method
        def unapply(r: Int): Option[Int] = {

            if (r % 5 == 0)
            {
                Some(r * 5)
            }
            else
                None

        }

        // Displays output
        println ("The Apply method returns : " + apply(20))
        println ("The Unapply method returns : " + unapply(35))
    }
}
```

**Output:**

```scala
The Apply method returns : 200.0
The Unapply method returns : Some(175)
```

这里，这个例子显示了 `GfG` 的提取器对象。对象 `GfG` 定义了两种方法 `apply` 和 `unapply`。`apply` 方法接受 `Double` 类型的参数。当我们调用 `apply` 方法时，传递的参数乘以 **10** 并返回相乘的数字。如果传递的值可被 **5** 整除，则 `unapply` 方法会分解参数，然后将传递的值乘以 **5** ，并返回 `(r*5)`，否则不返回任何值。

## Usage Of Scala Extractors

*   **使用具有模式匹配的提取器:**
    提取器可用于模式匹配。在模式匹配中比较提取器的对象时，`unapply` 方法将自动执行。
    **例:**

## Scala

```scala
// Scala program of extractors
// with pattern matching

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Assigning value to the
        // object
        val x = GfG(25)

        // Displays output of the
        // Apply method
        println(x)

        // Applying pattern matching
        x match
        {

            // unapply method is called
            case GfG(y) => println("The value is: "+y)
            case _ => println("Can't be evaluated")

        }
    }

    // Defining apply method
    def apply(x: Double) = x / 5

    // Defining unapply method
    def unapply(z: Double): Option[Double] =

        if (z % 5 == 0)
        {
            Some(z/5)
        }

        else None
}
```

**Output:**

```scala
5.0
The value is: 1.0
```

*   **注意:** 一个 `case class` 中已经自动生成了一个提取器，所以它可以和模式匹配一起自发使用。

*   **使用提取器进行测试:**
    为了使用提取器进行测试，可以返回一个 `Boolean` 类型。
    **例:**

## Scala

```scala
// Scala program of extractors
// to return a Boolean type

// Creating object
object GfG
{

    // Main method
    def main(args: Array[String])
    {

        // Defining unapply method
        def unapply(x:Int): Boolean = {

            if (x % 3 == 0)
            {
                true
            }
            else
                    false
        }

        // Displays output in Boolean type
        println ("The Unapply method returns : " + unapply(12))
        println ("The Unapply method returns : " + unapply(35))

    }
}
```

**Output:**

```scala
true
false
```

在这里，对象 `GfG` 定义了一个 `unapply` 方法。在调用 `unapply` 方法的过程中，如果传递的参数值除以 3 的余数为 0 则返回 **true**，否则返回 **false**。