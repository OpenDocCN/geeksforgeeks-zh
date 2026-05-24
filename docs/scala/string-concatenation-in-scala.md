# Scala 中的字符串串联

> 原文:[https://www . geesforgeks . org/string-concation-in-Scala/](https://www.geeksforgeeks.org/string-concatenation-in-scala/)

一个[字符串](https://www.geeksforgeeks.org/scala-string/)是一个字符序列。在 Scala 中，String 的对象是不可变的，这意味着一个常量，一旦创建就不能更改。当通过添加两个字符串来创建一个新字符串时，称为字符串串联。Scala 提供了 **concat()** 方法来连接两个字符串，这个方法返回一个使用两个字符串创建的新字符串。我们也可以使用“ **+** ”运算符来连接两个字符串。
**语法:**

```scala
*str1.concat(str2);*

Or

*"str1" + "str2";*
```

下面是连接两个字符串的示例。
**使用 concat()方法:**该方法将参数追加到字符串中。
**示例#1:**

## 斯卡拉

```scala
// Scala program to illustrate how to 
// concatenate strings
object GFG
{

    // str1 and str2 are two strings
    var str1 = "Welcome! GeeksforGeeks "
    var str2 = " to Portal"

    // Main function
    def main(args: Array[String])
    {

        // concatenate str1 and str2 strings
        // using concat() function
        var Newstr = str1.concat(str2);

        // Display strings 
        println("String 1:" +str1);
        println("String 2:" +str2);
        println("New String :" +Newstr);

        // Concatenate strings using '+' operator
        println("This is the tutorial" + 
                    " of Scala language" + 
                    " on GFG portal");
    }
}
```

**输出:**

```scala
String 1:Welcome! GeeksforGeeks 
String 2: to Portal
New String :Welcome! GeeksforGeeks  to Portal
This is the tutorial of Scala language on GFG portal
```

在上面的例子中，我们使用 concat()函数将第二个字符串连接到第一个字符串的末尾。弦 1 为**欢迎！极客之门**弦 2 是**到传送门**。在连接两个字符串后，我们得到新的字符串欢迎！极客登录门户网站。

**使用+运算符:**我们可以通过使用 **+** 运算符来添加两个字符串。
**例 2:**

## 斯卡拉

```scala
// Scala program to illustrate how to
// concatenate strings

// Creating object
object GFG
{
    // Main method
   def main(args: Array[String])
   {
        var str1 = "Welcome to ";
        var str2 =  "GeeksforGeeks";

        // Concatenating two string
        println("After concatenate two string: " + str1 + str2);
   }
}
```

**输出:**

```scala
After concatenate two string: Welcome toGeeksforGeeks
```

在上例中，字符串 1 是**欢迎来到**字符串 2 是**极客 forGeeks** 。通过使用+运算符连接两个字符串，我们可以在连接两个字符串后获得输出。