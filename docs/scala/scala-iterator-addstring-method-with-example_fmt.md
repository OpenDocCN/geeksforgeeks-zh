# Scala 迭代器 `addString()` 方法示例

> 原文：[https://www.geeksforgeeks.org/scala-iterator-addstring-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-addstring-method-with-example/)

`addString()` 方法属于 `AbstractIterator` 类的具体值成员。它在 `Iterator` 类中定义，用于将 Scala 迭代器的元素附加到字符串生成器中。

## 方法定义

```scala
def addString(b: StringBuilder): StringBuilder
```

**返回类型：** 返回添加了元素的字符串生成器。

## 示例 #1

```scala
// Scala program of addString()
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Creating an Iterator 
        val iter = Iterator(7, 6, 8, 1)

// Applying addString method 
        val result = iter.addString(new StringBuilder())

// Displays output
        println(result)

    }
}
```

**输出：**

```scala
7681
```

## 示例 #2

```scala
// Scala program of addString()
// method

// Creating object
object GfG
{

// Main method
    def main(args: Array[String])
    {

// Creating an Iterator 
        val iter = Iterator(7.7, 6.1, 8.6, 1.1)

// Applying addString method 
        val result = iter.addString(new StringBuilder())

// Displays output
        println(result)

    }
}
```

**输出：**

```scala
7.76.18.61.1
```