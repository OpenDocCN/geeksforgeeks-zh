# Kotlin | apply vs with

> 原文: [https://www.geeksforgeeks.org/kotlin-apply-vs-with/](https://www.geeksforgeeks.org/kotlin-apply-vs-with/)

## Kotlin: `apply`

在 [Kotlin](https://www.geeksforgeeks.org/introduction-to-kotlin/) 中，`apply` 是特定类型的扩展函数，并将其作用域设置为调用 `apply` 的对象。`apply` 在表达式中的对象引用上运行，并在完成时返回该对象引用。当然，它不仅仅是设置属性，还能做更多的事情，能够在返回之前评估复杂的逻辑。最后，它返回同一个对象，只是做了一些修改。

- `apply` 是一个特定类型的扩展函数。
- 需要对象引用来在表达式中运行。
- 完成时也返回一个对象引用。

**`apply` 的定义：**

```kt
inline fun <T> T.apply(block: T.() -> Unit): T {
    block()
    return this
}
```

**`apply` 的例子**

```kt
fun main(args: Array<String>) {
    data class GFG(var name1: String, var name2: String, var name3: String)
    // 实例化类的对象
    var gfg = GFG("Geeks", "for", "hi")
    // 调用 apply 函数来改变 name3 的值
    gfg.apply { this.name3 = "Geeks" }
    println(gfg)
}
```

**输出：**

```kt
GFG(name1=Geeks, name2=for, name3=Geeks)
```

在这里，`GFG` 类的第三个成员从 "hi" 变成了 "Geeks"。

## Kotlin: `with`

与 `apply` 一样，`with` 也用于更改实例的属性。但是这里我们不需要对象引用来运行，即：我们不需要 **点** 运算符来引用。

**`with` 的定义**

```kt
inline fun <T, R> with(receiver: T, block: T.() -> R): R {
    return receiver.block()
}
```

**`with` 的例子**

```kt
fun main(args: Array<String>) {
    data class GFG(var name1: String, var name2: String, var name3: String)
    var gfg = GFG("hello", "for", "hi")
    // 应用 with 函数
    with(gfg) {
        name1 = "Geeks"
        name3 = "Geeks"
    }
    println(gfg)
}
```

**输出：**

```kt
GFG(name1=Geeks, name2=for, name3=Geeks)
```

这里我们不需要任何 **点** 运算符，我们使用 `with` 扩展函数改变了 `GFG` 类对象的第一个和第三个变量的值。

## `apply` 和 `with` 的区别

- `with` **无需对象即可运行**，而 `apply` **需要一个对象来运行**。
- `apply` **在对象引用上运行**，但 `with` **仅将其作为参数传递**。