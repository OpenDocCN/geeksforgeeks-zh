# 在 Python 中模拟数字类型

> 原文: [https://www.geeksforgeeks.org/emulating-numeric-types-in-python/](https://www.geeksforgeeks.org/emulating-numeric-types-in-python/)

以下是可以定义来模拟数字类型对象的函数。

## 在相同类型的对象上实现二进制操作的方法

这些函数不会改变调用对象，而是在对调用对象执行某些操作后返回一个相同类型的新数值对象。以下是实现[算术二进制运算](https://www.geeksforgeeks.org/python-operators/)的方法。

| 方法 | 操作 |
| :--- | :--- |
| `object.__add__(self, other)` | `+` (加法) |
| `object.__sub__(self, other)` | `-` (减法) |
| `object.__mul__(self, other)` | `*` (乘法) |
| `object.__matmul__(self, other)` | `@` (矩阵乘法) |
| `object.__truediv__(self, other)` | `/` (真除法) |
| `object.__floordiv__(self, other)` | `//` (地板除) |
| `object.__mod__(self, other)` | `%` (模数或余数) |
| `object.__divmod__(self, other)` | [`divmod()`](https://www.geeksforgeeks.org/divmod-python-application/) |
| `object.__pow__(self, other[, modulo])` | `**` (幂) |
| `object.__lshift__(self, other)` | `<<` (按位左移) |
| `object.__rshift__(self, other)` | `>>` (按位右移) |
| `object.__and__(self, other)` | `&` (按位与运算) |
| `object.__xor__(self, other)` | `^` (异或运算) |
| `object.__or__(self, other)` | `|` (按位或运算) |

`__pow__()` 被定义为接受第三个可选参数，以便支持 `pow()` 函数的三进制版本。此外，如果上述任何方法不支持该操作，则应返回 `NotImplemented`。

## 在不同类型的对象上实现二进制操作的方法

如果左侧对象（可折叠对象）的类型不同，则可以使用以下方法执行[算术二进制运算](https://www.geeksforgeeks.org/python-operators/)：

| 方法 | 操作 |
| :--- | :--- |
| `object.__radd__(self, other)` | `+` (加法) |
| `object.__rsub__(self, other)` | `-` (减法) |
| `object.__rmul__(self, other)` | `*` (乘法) |
| `object.__rmatmul__(self, other)` | `@` (矩阵乘法) |
| `object.__rtruediv__(self, other)` | `/` (真除法) |
| `object.__rfloordiv__(self, other)` | `//` (地板除) |
| `object.__rmod__(self, other)` | `%` (模数或余数) |
| `object.__rdivmod__(self, other)` | [`divmod()`](https://www.geeksforgeeks.org/divmod-python-application/) |
| `object.__rpow__(self, other[, modulo])` | `**` ([`pow()`](https://www.geeksforgeeks.org/pow-in-python/) 或数的幂) |
| `object.__rlshift__(self, other)` | `<<` (按位左移) |
| `object.__rrshift__(self, other)` | `>>` (按位右移) |
| `object.__rand__(self, other)` | `&` (按位与运算) |
| `object.__rxor__(self, other)` | `^` (异或运算) |
| `object.__ror__(self, other)` | `|` (按位或运算) |

例如，如果在 `a.__sub__(b)` 中，从 `b` 开始，`a` 不是数字类型，那么这个方法将返回 `NotImplemented`，然后为了执行 `a - b`，我们将调用 `b.__rsub__(a)`。

## 实现算术赋值运算的方法

这些方法用于实现[算术赋值运算](https://www.geeksforgeeks.org/python-operators/)。它们不会返回新的对象，而是在调用对象本身时分配新的值。像 `x.__imul__(y)` 将作为 `x = x * y` 执行。以下是每种方法的相应操作。

| 方法 | 操作 |
| :--- | :--- |
| `object.__iadd__(self, other)` | `+=` (加法赋值) |
| `object.__isub__(self, other)` | `-=` (减法赋值) |
| `object.__imul__(self, other)` | `*=` (乘法赋值) |
| `object.__imatmul__(self, other)` | `@=` (矩阵乘法赋值) |
| `object.__itruediv__(self, other)` | `/=` (真除法赋值) |
| `object.__ifloordiv__(self, other)` | `//=` (地板除赋值) |
| `object.__imod__(self, other)` | `%=` (模数或余数赋值) |
| `object.__ipow__(self, other[, modulo])` | `**=` ([`pow()`](https://www.geeksforgeeks.org/pow-in-python/) 赋值) |
| `object.__ilshift__(self, other)` | `<<=` (按位左移赋值) |
| `object.__irshift__(self, other)` | `>>=` (按位右移赋值) |
| `object.__iand__(self, other)` | `&=` (按位与运算赋值) |
| `object.__ixor__(self, other)` | `^=` (按位异或赋值) |
| `object.__ior__(self, other)` | `|=` (按位或运算赋值) |

## 实现一元算术运算的方法

以下是实现一元算术运算的方法，如，一个数的负数，一个数的倒数等。

| 方法 | 操作 |
| :--- | :--- |
| `object.__neg__(self)` | `-` (一元减) |
| `object.__pos__(self)` | `+` (一元加号) |
| `object.__abs__(self)` | [`abs()`](https://www.geeksforgeeks.org/abs-in-python/#:~:text=Itertools.Permutations()-,abs()%20in%20Python,absolute%20value%20of%20a%20number.&text=If%20the%20argument%20is%20an,be%20a%20floating%20point%20number.) 内置功能 |
| `object.__invert__(self)` | `~` (一个数的补码) |

## 其他一些重要的方法

| 方法 | 描述 |
| :--- | :--- |
| `object.__index__(self)` | 调用以实现 `operator.index()` 函数，也用于将数值类型对象转换为整数类型，或者我们可以说，如果 `__int__()`，`__float__()` 或 `__complex__()` 没有定义，那么 `int()`，`float()` 和 `complex()` 就会下降在 `__index__()` 下。 |
| `object.__round__(self, ndigits)` | 要实现 [`round()` 函数](https://www.geeksforgeeks.org/round-function-python/#:~:text=Python%20in%202020%3F-,round()%20function%20in%20Python,number%20to%20the%20nearest%20integer.)，第二个可选参数告诉最多多少个小数位我们想要取整数值。 |
| `object.__trunc__(self)` | 要实现 [`trunc()` 功能。](https://www.geeksforgeeks.org/g-fact-35-truncate-in-python/) |
| `object.__floor__(self)` | 要实现 [`floor()` 功能。](https://www.geeksforgeeks.org/floor-ceil-function-python/#:~:text=The%20method%20ceil()%20in,integer%20not%20less%20than%20x.) |
| `object.__ceil__(self)` | 要实现 [`ceil()` 功能。](https://www.geeksforgeeks.org/floor-ceil-function-python/#:~:text=The%20method%20ceil()%20in,integer%20not%20less%20than%20x.) |