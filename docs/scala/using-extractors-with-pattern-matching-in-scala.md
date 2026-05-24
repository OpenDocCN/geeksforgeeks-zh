# 在 Scala 中使用具有模式匹配的提取器

> 原文:[https://www . geesforgeks . org/using-extractors-with-pattern-matching-in-Scala/](https://www.geeksforgeeks.org/using-extractors-with-pattern-matching-in-scala/)

Scala Extractor 被定义为一个对象，它的一部分是一个名为 unapply 的方法。[提取器](https://www.geeksforgeeks.org/scala-extractors/)可用于[模式匹配](https://www.geeksforgeeks.org/scala-pattern-matching/)。在模式匹配中比较提取器的对象时，不应用方法将自动执行。

下面是模式匹配提取器的例子。
**例 1:**

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

在上面的例子中，对象名是 GFG，我们也在使用不应用方法和匹配表达式应用案例类。

**例 2:**

```scala
// Scala program of extractors 
// with pattern matching 

// Creating object 
object GFG
{ 

    // Main method 
    def main(args: Array[String]) 
    { 

        val x = GFG(15)
        println(x)

        x match
        {
            case GFG(num) => println(x + 
                        " is bigger two times than " + num)

            // Unapply is invoked
            case _ => println("not calculated")
    }
}
def apply(x: Int) = x * 2
def unapply(z: Int): Option[Int] = if (z % 2 == 0) 
                                    Some(z/2) else None
} 
```

**Output:**

```scala
30
30 is bigger two times than 15

```

使用 match 语句比较提取器对象时，将自动执行 unapply 方法。
**注意:**一个 Case 类中已经有了提取器，所以可以通过模式匹配自发地使用。