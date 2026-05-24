# Scala Option

> 原文：`https://www.geeksforgeeks.org/scala-option/`

Scala 中的 `Option` 指的是一种指定类型的单元素或无元素的载体。当一个方法返回一个甚至可以为空的值时，就使用了 `Option`，即定义的方法返回一个 `Option` 的实例，而不是返回单个对象或空值。

## 重要点

- 这里返回的 `Option` 实例可以是 Scala 中 `Some` 类或 `None` 类的实例，其中 `Some` 和 `None` 是 `Option` 类的子类。
- 当获得给定键的值时，就会生成 `Some` 类。
- 当没有获得给定键的值时，则生成 `None` 类。

## 示例

```scala
// Scala program for Option

// Creating object
object option
{

    // Main method
    def main(args: Array[String])
    {

        // Creating a Map
        val name = Map("Nidhi" -> "author",
                       "Geeta" -> "coder")

        // Accessing keys of the map
        val x = name.get("Nidhi")
        val y = name.get("Rahul")

        // Displays Some if the key is
        // found else None
        println(x)
        println(y)
    }
}
```

**Output:**

```scala
Some(author)
None
```

在这里，值 `Nidhi` 的键是这样找到的，`Some` 是为它返回的，但是值 `Rahul` 的键不是这样找到的，`None` 是为它返回的。

## 获取可选值的不同方式

### 使用模式匹配

**示例:**

```scala
// Scala program for Option
// with Pattern matching

// Creating object
object pattern
{

    // Main method
    def main(args: Array[String])
    {

        // Creating a Map
        val name = Map("Nidhi" -> "author",
                       "Geeta" -> "coder")

        //Accessing keys of the map
        println(patrn(name.get("Nidhi")))
        println(patrn(name.get("Rahul")))
    }

    // Using Option with Pattern
    // matching
    def patrn(z: Option[String]) = z match
    {

        // for 'Some' class the key for
        // the given value is displayed
        case Some(s) => (s)

        // for 'None' class the below string
        // is displayed
        case None => ("key not found")
    }
}
```

**Output:**

```scala
author
key not found
```

这里，我们已经在 Scala 中使用了带有[模式匹配](https://www.geeksforgeeks.org/scala-pattern-matching/)的 `Option`。

### getOrElse() 方法

此方法用于在值存在时返回该值，或在值不存在时返回一个默认值。对于 `Some` 类返回其值，对于 `None` 类返回默认值。

**示例:**

```scala
// Scala program of using
// getOrElse method

// Creating object
object get
{

    // Main method
    def main(args: Array[String])
    {

        // Using Some class
        val some:Option[Int] = Some(15)

        // Using None class
        val none:Option[Int] = None

        // Applying getOrElse method
        val x = some.getOrElse(0)
        val y = none.getOrElse(17)

        // Displays the key in the
        // class Some
        println(x)

        // Displays default value
        println(y)
    }
}
```

**Output:**

```scala
15
17
```

在这里，分配给 `None` 的默认值是 17，所以它返回给 `None` 类。

### isEmpty() 方法

此方法用于检查 `Option` 是否有值。

**示例:**

```scala
// Scala program of using
// isEmpty method

// Creating object
object check
{

    // Main method
    def main(args: Array[String])
    {

        // Using Some class
        val some:Option[Int] = Some(20)

        // Using None class
        val none:Option[Int] = None

        // Applying isEmpty method
        val x = some.isEmpty
        val y = none.isEmpty

        // Displays true if there
        // is a value else false
        println(x)
        println(y)
    }
}
```

**Output:**

```scala
false
true
```

在这里，`isEmpty` 为 `Some` 类返回 `false`（因为非空），但为 `None` 返回 `true`（因为空）。