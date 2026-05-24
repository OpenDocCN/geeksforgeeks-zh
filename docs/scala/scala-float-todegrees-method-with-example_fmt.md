# Scala Float toDegrees()方法示例

> 原文: [https://www.geeksforgeeks.org/scala-float-todegrees-method-with-example/](https://www.geeksforgeeks.org/scala-float-todegrees-method-with-example/)

`toDegrees`方法用于将以弧度测量的角度转换为以度测量的近似等效角度。

## 方法定义与返回类型

**方法定义:** `(number).toDegrees`

**返回类型:** 返回度数的转换值。

## 示例 #1

```scala
// Scala program of Float toDegrees()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying toDegrees method
        val result = (56).toDegrees

// Displays output
        println(result)

}
}
```

**输出:**

```scala
3208.5637
```

## 示例 #2

```scala
// Scala program of Float toDegrees()
// method

// Creating object
object GfG
{

// Main method
    def main(args:Array[String])
    {

// Applying toDegrees method
        val result = (3.14).toDegrees

// Displays output
        println(result)

}
}
```

**输出:**

```scala
179.90874767107852
```