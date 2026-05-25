# 如何检查 Kotlin 中的“lateinit”变量是否已经初始化？

> 原文: [https://www.geeksforgeeks.org/how-to-check-if-a-lateinit-variable-has-been-initialized-or-not-in-kotlin/](https://www.geeksforgeeks.org/how-to-check-if-a-lateinit-variable-has-been-initialized-or-not-in-kotlin/)

在 Kotlin 中，`lateinit` 关键字用于那些在声明之后初始化的变量，或者我们可以说延迟初始化的变量叫做 `lateinit` 变量。`lateinit` 关键字用于我们确定变量将在使用前被初始化的情况。如果我们在使用一个 `lateinit` 变量之前没有初始化它，就会给出一个“lateinit 属性没有初始化”的错误。在使用 `lateinit` 变量之前，可以借助 `isInitialized()` 方法检查该变量是否已经初始化。如果 `lateinit` 属性已经初始化，该方法将返回 `true`，否则将返回 `false`。

您可以通过以下方式轻松做到这一点:

> `variableName.isInitialized`

或者:

> `this::variableName.isInitialized`

但是，如果您在一个侦听器或内部类中，请执行以下操作:

> `this@OuterClassName::variableName.isInitialized`

## 例如:

```kt
class Tutorial {

    lateinit var tutorialName : String

    fun initializeName(){
        println(this::tutorialName.isInitialized)

        // initializing name
        tutorialName = "GFG Android Course"
        println(this::tutorialName.isInitialized)
    }
}

fun main() {
    Tutorial().initializeName();
}
```

**输出:**

```
false
true
```