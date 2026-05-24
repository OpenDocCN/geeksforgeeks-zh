# Scala Int is validaint()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-int-is validaint-method-with-example/](https://www.geeksforgeeks.org/scala-int-isvalidint-method-with-example/)

如果指定的整数为零或在 isValidInt 最小值和最大值的范围内，则使用**is validaint()**方法返回真；否则返回 false。

```scala
Method Definition: (Int_Number).isValidIntReturn 
Type: It returns true if the specified number is either zero or lies within 
      the range of scala.int MinValue and MaxValue; otherwise returns false.
```

**例 1:**

## 斯卡拉

```scala
// Scala program of Int isValidInt()
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidInt method
        val result = (0).isValidInt

        // Displays output
        println(result)

    }
}
```

**Output:** 

```scala
true
```

**例 2:**

## 斯卡拉

```scala
// Scala program of Int isValidInt()
// method

// Creating object
object GfG
{

    // Main method
    def main(args:Array[String])
    {

        // Applying isValidInt method
        val result = (5.9).isValidInt

        // Displays output
        println(result)

    }
}
```

**Output:** 

```scala
false
```