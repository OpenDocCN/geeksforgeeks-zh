# Scala |文字

> 原文:[https://www.geeksforgeeks.org/scala-literals/](https://www.geeksforgeeks.org/scala-literals/)

任何可以赋给变量的常量值都称为文字/常量。**文字**是一系列用于描述代码中常量值的符号。Scala 中有许多类型的文字，即字符文字、字符串文字、多行字符串文字、布尔文字、整数文字和浮点文字。

### 文字的类型

1.  **整数文字:**
    当在整数的末尾加上后缀 L 或 L 时，整数文字通常为 Int 类型或 Long 类型。类型 *Int* 和类型 *Long* 都是整数。
    **注:**
    *   Int 类型的范围是从(-231 到 230)。
    *   Long 类型的范围是(-263 到 262)。
    *   当一个整数文字有一个超出这个范围的数字时，就会出现编译时错误。

*   **十进制文字:**
    这里，允许的位数是从 0 到 9。

    ```scala
    val x = 37
    ```

    *   **Hexa-decimal literals:**
    Here, the allowed digits are from 0 to 9 and characters used are from a to f. We can use uppercase as well as lowercase characters.

    ```scala
    // The hexa-decimal number should be prefix
    // with 0X or 0x.
    val x = 0xFFF
    ```

    **示例:**

    ```scala
    // Scala program of integer
    // literals

    // Creating object
    object integer
    {

        // Main method
        def main(args: Array[String])
        {

            // decimal-form literal
            val a = 46

            // Hexa-decimal form literal
            val b = 0xfF

            // Displays results in
            // integer form
            println(a)
            println(b)
        }
    }
    ```

    **Output:**

    ```scala
    46
    255

    ```

    **注:**字面的八进制形式已经过时。

    *   **Floating Point Literals :**
    This type of literals are of type Double as well as type Float when a suffix F or f is added at the end and we can even specify Double type by suffixed with d or D.

    ```scala
    val x = 3.14159
    ```

    **示例:**

    ```scala
    // Scala program of floating
    // point literals

    // Creating object
    object double
    {

        // Main method
        def main(args: Array[String])
        {

            // decimal-form literal
            val a = 3.156

            // It is also a decimal 
            // form of the literal
            val b = 0123.34

            // Displays results
            println(a)
            println(b)
        }
    }
    ```

    **Output:**

    ```scala
    3.156
    123.34

    ```

    这里，我们不能指定八进制或十六进制形式的文字。

    *   **Character Literals :**
    character literals are either uni-code character which are printable or are represented by escape sequences.

    ```scala
    val x = 'b' 
    //character literal in a single quote.
    ```

    ```scala
    val x = '\u0051' 
    //uni-code representation of character literal,
    //This uni-code represents Q.
    ```

    ```scala
    val x = '\n' 
    //Escape sequence in character literals
    ```

    **示例:**

    ```scala
    // Scala program of character
    // literal

    // Creating object
    object literal
    {

        // Main method
        def main(args: Array[String])
        {
            // Creating a character literal
            // in single quote
            val x = 'b'

            // uni-code representation of
            // character literal
            val y = '\u0051'

            // Escape sequence in character
            // literals
            val z = '\n'

            // Displays results
            println(x)
            println(y)
            println(z)
        }
    }
    ```

    **Output:**

    ```scala
    b
    Q

    ```