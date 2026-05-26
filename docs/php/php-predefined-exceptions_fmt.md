# PHP - 预定义异常

> Original: [https://www.geeksforgeeks.org/php-predefined-exceptions/](https://www.geeksforgeeks.org/php-predefined-exceptions/)

PHP 中提供了预定义的异常，以便更有效地处理异常，但本文的先决条件是学习异常处理[、https://www.geeksforgeeks.org/exception-handling-in-php/和](https://www.geeksforgeeks.org/exception-handling-in-php/)

**异常：** 此功能在 PHP 版本 5 和 7 中可用。在版本 7 中，它为每个用户定义的异常行为一个基类，但在版本 5 中，它为每个存在的异常行为一个基类。

`Exception` 类有 10 个方法和 4 个属性。

这四个属性是：

| 简短描述 | 数据类型 | 完整描述 |
| --- | --- | --- |
| `message` | String | 表示异常发生时要显示的消息。 |
| `code` | Int | 表示异常发生时的异常代码。 |
| `file` | String | 表示发生异常的文件名。 |
| `line` | Int | 表示发生异常的行号。 |

`Exception` 的 10 个方法是：

| 函数名 | 参数数量 | 参数名 | 返回类型 | 描述 |
| --- | --- | --- | --- | --- |
| `__construct` | 3 | `Message(String)`, `code(Int)`, `previous(Throwable)` | void | 构造异常 |
| `getMessage` | 0 | - | String | 返回异常发生时要显示的消息。 |
| `getPrevious` | 0 | - | Throwable | 返回前一个异常 |
| `getCode` | 0 | - | mixed | 返回生成的异常代码 |
| `getFile` | 0 | - | String | 返回发生异常的文件 |
| `getLine` | 0 | - | Int | 返回异常发生的行号 |
| `getTrace` | 0 | - | Array | 返回堆栈跟踪 |
| `getTraceAsString` | 0 | - | String | 以字符串形式返回堆栈跟踪 |
| `__toString` | 0 | - | String | 以字符串形式返回异常信息 |
| `__clone` | 0 | - | void | 克隆生成的异常 |

**ErrorException：** `ErrorException` 类只是 `Exception` 类的扩展版本。 它只有一个新添加的属性，其余是从 `Exception` 类继承的。 有两个新的附加方法，一个用于构造异常，另一个用于返回发生的异常的严重性。

附加的一个属性是：

| 简短描述 | 数据类型 | 完整描述 |
| --- | --- | --- |
| `severity` | Int | 用于指示发生的异常的严重性。 |

附加的方法是：

| 函数名 | 参数数量 | 参数名 | 返回类型 | 描述 |
| --- | --- | --- | --- | --- |
| `__construct` | 6 | `Message (String)`, `code`, `Severity (Int)`, `file name (String)`, `Line number (Int)`, `previous exception (Throwable)` | void | 构造异常 |
| `getSeverity` | 0 | - | Int | 此函数返回异常的严重性 |

**Error：** PHP 中生成的所有内部错误都来自此基类。 它具有类似于 `Exception` 类的功能。 它有四个属性和十个方法。 函数名相同，属性也都相同。 这两个类的不同之处在于，`Exception` 类方法返回有关异常的信息，而 `Error` 类返回有关 PHP 中内部错误的信息。

**ArgumentCountError：** 当预期数量的参数没有作为参数传递给用户定义的函数时，就开始使用它。 它是 `TypeError` 类的扩展，所有方法和属性都继承自 `TypeError` 类。

**ArithmeticError：** 当在 PHP 中执行算术计算时发生异常，则会使用此类。 在 PHP 版本 7 中，当发生此类错误时，还会尝试负值位移位。 此类是类 `Error` 的扩展，因此所有方法都是刚从类 `Error` 继承的属性。

**AssertionError：** 如果通过函数 `assert()` 执行了断言并导致异常，则开始使用此类。 函数 `assert()` 用于计算断言，该函数返回布尔值。 当涉及到调试时，此函数是一个有用的功能。

**DivisionByZeroError：** 如果一个数字被零除，则使用这个类，它是 `ArithmeticError` 类的扩展。

**CompileError：** 如果在编译过程中发生错误，则编译错误发生在哪个类 `CompileError` 类。 通常，编译错误是致命错误。 此类是类 `Error` 的扩展。

**ParseError：** 在解析 PHP 代码并发生异常时，将使用此类。 它是 `CompileError` 类的扩展。 像 `eval()` 这样的函数是一种语言构造，它会生成这种类型的异常。

**TypeError：** 此类是类 `Error` 的扩展。 这类例外的产生主要有三个原因。

*   函数中声明的参数类型与传递的参数类型不匹配。
*   声明的函数的返回类型与要返回的类型不匹配。
*   有一些内置的 PHP 函数接受受限和特定类型的参数。 如果传递给它们的参数类型或数量错误，则会发生此异常。