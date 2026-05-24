# Scala 迭代器 hasNext()方法，示例

> 原文:[https://www . geeksforgeeks . org/Scala-iterator-hasnext-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-hasnext-method-with-example/)

**hasNext()** 方法属于类*抽象迭代器*的抽象值成员。它在类*迭代器*中定义。它检查下一个元素是否可用。

> **方法定义:**抽象定义 hasNext: Boolean
> 
> **返回类型:**如果有 Next 元素则返回 true，否则返回 false。

**示例#1:**

```scala
// Scala program of hasNext()
// method

// Creating object
object GfG
{ 

    // Main method
    def main(args:Array[String])
    {

        // Creating an Iterator 
        val iter = Iterator(2, 3, 4, 5)

        // Applying hasNext method 
        val result = iter.hasNext

        // Displays output
        println(result)

    }
}
```

**输出:**

```scala
true

```