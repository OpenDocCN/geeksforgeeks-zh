# Scala 列表产品()方法示例

> 原文:[https://www . geeksforgeeks . org/Scala-list-product-method-with-example/](https://www.geeksforgeeks.org/scala-list-product-method-with-example/)

利用**乘积()**方法寻找所述列表中所有元素的乘积。

> **方法定义:** def 积(数:数学。数字[B]): B
> 
> **返回类型:**返回所述列表中所有元素的乘积。

**示例#1:**

```scala
// Scala program of product()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 2, 3, 4, 5)

        // Applying product method
        val result = m1.product

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
120

```

**例:2#**

```scala
// Scala program of product()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating a list
        val m1 = List(1, 0)

        // Applying product method
        val result = m1.product

        // Displays output
        println(result)

    }
}
```

**Output:**

```scala
0

```