# Scala 迭代器`product()`方法示例

> 原文: [https://www.geeksforgeeks.org/scala-iterator-product-method-with-example/](https://www.geeksforgeeks.org/scala-iterator-product-method-with-example/)

`product()`方法属于抽象迭代器类的具体值成员。它用于将所述集合的所有元素相乘。

> **方法定义:** `val result = iter.product`
> 
> **返回类型:** 返回所述迭代器所有元素相乘得到的结果。

## 示例#1:

```scala
// Scala program of product()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating a Iterator 
        val iter = Iterator(1, 2, 3, 4, 5, 6)

// Applying product method 
        val result = iter.product

// Displays output
        println(result)

}
}
```

**Output:**

```scala

```

## 例 2:

```scala
// Scala program of product()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Creating a Iterator 
        val iter = Iterator(0, 1)

// Applying product method 
        val result = iter.product

// Displays output
        println(result)

}
}
```

**Output:**

```scala

```