# Scala String 替换()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-string-replace-method-with-example/](https://www.geeksforgeeks.org/scala-string-replace-method-with-example/)

**replace()** 方法用于用参数中声明的新字符替换字符串的旧字符。

> **方法定义:**字符串替换(char oldChar，char newChar)
> **返回类型:**用新字符替换旧字符后返回指定的字符串。

**示例#1:**

```scala
// Scala program of replace()
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying replace method
val result = "Nidhi".replace('N', 'n')

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
nidhi

```

**例 2:**

```scala
// Scala program of replace()
// method

// Creating object
object GfG
{  

// Main method
def main(args:Array[String])
{

// Applying replace method
val result = "Nidhi".replace('h', '#')

// Displays output
println(result)

   }
} 
```

**Output:**

```scala
Nid#i

```