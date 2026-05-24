# 斯卡拉弦

> 原文:[https://www.geeksforgeeks.org/scala-string/](https://www.geeksforgeeks.org/scala-string/)

一 ***串*** 是一个字符序列。在 Scala 中，String 的对象是不可变的，这意味着一个常量，一旦创建就不能更改。

#### 在 Scala 中创建字符串

在 Scala 中创建字符串有两种方法:

*   这里，当编译器遇到一个字符串文字并创建一个字符串对象字符串时。
    **语法:**

```scala
var str = "Hello! GFG"
or
val str = "Hello! GFG"
```

*   这里，在满足字符串文字之前指定一个字符串类型。
    **语法:**

```scala
var str: String = "Hello! GFG"
or
val str: String = "Hello! GFG"
```

**注意:**如果需要追加到原字符串，那么使用 ***StringBuilder*** 类。
**例:**

## 斯卡拉

```scala
// Scala program to illustrate how to 
// create a string
object Main
{

    // str1 and str2 are two different strings
    var str1 = "Hello! GFG"
    val str2: String = "GeeksforGeeks"
    def main(args: Array[String]) 
    {

        // Display both strings
        println(str1);
        println(str2);
    }
}
```

**输出:**

```scala
Hello! GFG
GeeksforGeeks
```

#### 获取字符串的长度

存取器方法是用于查找对象信息的方法。所以，一个 **length()** 方法是 Scala 中的访问器方法，用来求给定字符串的长度。或者换句话说，length()方法返回字符串对象中存在的字符数。
**语法:**

```scala
var len1 = str1.length();
```

**示例:**

## 斯卡拉

```scala
// Scala program to illustrate how to 
// get the length of the given string
object Main 
{

    // str1 and str2 are two strings
    var str1 = "Hello! GFG"
    var str2: String = "GeeksforGeeks"

    // Main function
    def main(args: Array[String]) 
    {

        // Get the length of str1 and str2 strings
        // using length() function
        var LEN1 = str1.length();
        var LEN2 = str2.length();

        // Display both strings with their length
        println("String 1:" + str1 + ", Length :" + LEN1);
        println("String 2:" + str2 + ", Length :" + LEN2);
    }
}
```

**输出:**

```scala
String 1:Hello! GFG, Length :10
String 2:GeeksforGeeks, Length :13
```

#### 在 Scala 中连接字符串

当通过添加两个字符串来创建一个新字符串时，称为字符串串联。Scala 提供 **concat()** 方法来连接两个字符串，这个方法返回一个使用两个字符串创建的新字符串。您也可以使用“+”运算符来连接两个字符串。
**语法:**

```scala
str1.concat(str2);
```

或
**语法:**

```scala
"welcome" + "GFG"
```

**示例:**

## 斯卡拉

```scala
// Scala program to illustrate how to 
// concatenate strings
object Main 
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

#### 正在创建格式字符串

当您需要格式化字符串中的数字或值时，您将使用 **printf()** 或 **format()** 方法。除了这些方法之外，String 类还提供了一个名为 format()的方法，这个方法返回一个 String 对象而不是 PrintStream 对象。
**例:**

## 斯卡拉

```scala
// Scala program to illustrate how to 
// Creating format string
object Main 
{

    // two strings
    var A_name = "Ankita "
    var Ar_name = "Scala|Strings"
    var total = 130

    // Main function
    def main(args: Array[String]) 
    {

        // using format() function
        println("%s, %s, %d".format(A_name, Ar_name, total));
    }
}
```

**输出:**

```scala
Ankita , Scala|Strings, 130
```

#### 一些重要的字符串函数

| 功能 | 描述 |
| **char charAt(int index)** | 该函数返回给定索引处的字符。 |
| **字符串替换(char ch1，char ch2)** | 这个函数返回一个新的字符串，其中 ch1 的元素被 ch2 替换。 |
| **字符串[]拆分(字符串 reg)** | 这个函数在给定正则表达式的匹配项周围拆分字符串。 |
| **字符串子串(int i)** | 此函数返回一个新字符串，它是给定字符串的子字符串。 |
| **细绳修剪()** | 这个函数返回一个字符串的副本，去掉开头和结尾的空白。 |
| **布尔 startsWith(字符串前缀)** | 该函数用于检查给定的字符串是否以指定的前缀开头。 |