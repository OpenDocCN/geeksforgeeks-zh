# 覆盖 Scala 中的 toString()方法

> 原文:[https://www . geeksforgeeks . org/overriding-tostring-method-in-Scala/](https://www.geeksforgeeks.org/overriding-tostring-method-in-scala/)

考虑以下 Scala 程序:

```scala
// Scala Program without override toString method

// Creating Class
class Language(LangArticle: Int, LangName: String) 
{

    // Defining getLangArticle method
    def getLangArticle() : Int = {

        return LangArticle;
    }

    // Defining getLangName method
    def getLangName() : String = {

        return LangName;
    }

}

// Creating object
object GFG 
{
    // Main method
    def main(args: Array[String])
    {

        var language = new Language(50, "Scala");

        println(language)

    }
}
```

**输出:**

```scala
Language@506e1b77

```

输出是类名，然后是' at '符号，最后是对象的 hashCode。Scala 中的所有类都直接或间接继承自对象类。对象类有一些基本的方法，比如 clone()，toString()，equals()，..等等。Object 中默认的 toString()方法打印“类名@哈希代码”。我们可以在类中重写 toString()方法来打印正确的输出。下面是重写 toString 方法的示例。

```scala
// Scala Program to override toString method

// Creating Class
class Language(LangArticle: Int, LangName: String) 
{

    // Defining getLangArticle method
    def getLangArticle() : Int = {

        return LangArticle;
    }

    // Defining getLangName method
    def getLangName() : String = {

        return LangName;
    }

    // Overriding tostring method
    override def toString() : String = {

        return "[Total Article : " + LangArticle + 
                ", Language Name = " + LangName+"]";
    }

}

// Creating object
object GFG 
{
    // Main method
    def main(args: Array[String])
    {

        var language = new Language(50, "Scala");

        println(language)

    }
}
```

**输出:**

```scala
[Total Article : 50, Language Name = Scala]

```

在上面的示例中，语言类正在重写 toString()方法并返回字符串值。这个方法有属性名和值。该类定义了两个变量 LangArticle 和 LangName 以及三个方法:getLangArticle、getLangName 和 toString。 **getLangArticle** 取一个整数参数并返回值。 **getLangName** 接受一个字符串参数并返回一个值。**另一方面，toString** 不接受任何参数，但返回一个 String 值。由于 toString 重写了预定义的 toString 方法，因此必须用重写标志对其进行标记。

**注意:**当我们覆盖任意超类方法时。我们应该在方法前使用**覆盖**关键字(即:覆盖 def toString())。