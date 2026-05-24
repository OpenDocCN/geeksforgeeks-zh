# Scala 提取器

> 原文:[https://www.geeksforgeeks.org/scala-extractors/](https://www.geeksforgeeks.org/scala-extractors/)

在**中，标量提取器**被定义为一个对象，该对象有一个名为**的方法，不应用**作为其一部分。这个方法提取一个对象并返回属性。这种方法也用于模式匹配和部分函数。提取器还解释了**应用**方法，该方法接受参数并构造一个对象，因此有助于构造值。*不敷*法与*敷*法的施工程序相反。

**退单方式的退回类型可以选择如下:**

*   如果是检查程序，则返回一个*布尔*类型。
*   如果过程只返回一个类型为 T 的子值，则返回一个选项[T]。
*   如果该过程返回 T1、T2、…、Tn 类型的各种子值，则返回可选元组，即选项[(T1、T2、…、Tn)]。
*   如果过程返回不可预测数量的值，则提取器可以用返回选项[序列[T]]的*不可应用序列*来定义。

**示例:**

## 斯卡拉

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

这里，这个示例显示了名称的提取器对象。对象名称定义了两种方法*应用*和*不应用*。apply 方法接受括号中指定的参数，并创建方法中指定的值。名字和姓氏加上中间的**库马里**(中间名)被返回。unapply 方法按照指定的方式分解参数，并将 firstname 对象返回到提取器中。如果作为参数传递名字和姓氏，则返回一对字符串，否则不返回任何字符串。

**示例:**

## 斯卡拉

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

这里，这个例子显示了 GFG 的提取器对象。对象 GFG 定义了两种方法*应用*和*不应用*。apply 方法接受双精度类型的参数。当我们调用*应用*方法时，传递的参数乘以 **10** 并返回相乘的数字。如果传递的值可被 **5** 整除，则 *unapply* 方法会中断参数，然后将传递的值乘以 **5** ，并返回(r*5)否则不返回任何值。

Usage Of Scala Extractors

*   **使用具有模式匹配的提取器:**
    提取器可用于模式匹配。在模式匹配中比较提取器的对象时，*不应用*方法将自动执行。
    **例:**

## 斯卡拉

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

*   **注意:**一个案例类中已经有了一个提取器，所以它可以和模式匹配一起自发使用。

*   **使用提取器进行测试:**
    为了使用提取器进行测试，返回一个布尔类型。
    **例:**

## 斯卡拉

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

在这里，对象 *GFG* 定义了一个不适用的方法。在调用*不应用*方法的过程中，如果值除以 3 返回**真**否则返回**假**，则传递参数。