# Python Functools – `update_wrapper()`

> 原文: [https://www.geeksforgeeks.org/python-functools-update_wrapper/](https://www.geeksforgeeks.org/python-functools-update_wrapper/)

Python 中的 `functools` 模块处理**高阶函数**，也就是对函数进行操作（作为参数）或返回函数以及其他此类可调用对象的函数。`functools` 模块提供了多种方法，如 `cached_property(func)`, `cmp_to_key(func)`, `lru_cache(func)`, `wraps(func)` 等。值得注意的是，这些方法以函数作为参数。

在本文中，我们将讨论 `functools` 模块提供的 `update_wrapper()` 方法的目的和应用。此方法用于更新包装函数的元数据，以反映包装函数的元数据，从而提高代码的可读性和重用性。`update_wrapper()` 方法采用以下参数：

## 语法

`@functools.update_wrapper(wrapper, wrapped, assigned=WRAPPER_ASSIGNMENTS, updated=WRAPPER_UPDATES)`

## 参数

1.  `wrapper`: 一个包装器功能。
2.  `wrapped`: 被包装的功能或包装的功能。
3.  `assigned`: 包装函数的属性，作为元组赋给包装函数的匹配属性（可选参数）。
4.  `updated`: 包装函数的属性，相对于作为元组的原始函数属性进行更新（可选参数）。

为了更好地理解这个方法，让我们观察几个在 Python 中使用**装饰器和 `partial`** 的例子。

## 例 1

```py
# Defining the decorator
def hi(func):
    def wrapper():
        "Hi has taken over Hello Documentation"
        print("Hi geeks")
        func()
    return wrapper

@hi
def hello():
    "this is the documentation of Hello Function"
    print("Hey Geeks")

# Driver Code
print(hello.__name__)
print(hello.__doc__)
help(hello)
```

**输出:**

```py
wrapper
Hi has taken over Hello Documentation
Help on function wrapper in module __main__:

wrapper()
    Hi has taken over Hello Documentation
```

在上例中，当我们使用装饰器函数 `hi` 并用它的包装器包装 `hello` 时，函数 `hello` 的**模块级常量**，如 `__name__`、`__doc__` 等，被 `hi` 中包装器的包装所取代。

使用 `functools` 模块中的 `partial` 时也会出现同样的情况。让我们看一个例子：

## 例 2

```py
import functools

def divide(a, b):
    "Original Documentation of Divide"
    return a / b

half = functools.partial(divide, b=2)
oneThird = functools.partial(divide, b=3)

try:
    print(half.__name__)
except AttributeError:
    print('No Name')
print(half.__doc__)
```

**输出:**

> No Name
> partial(func, *args, **keywords) - new function with partial application
> of the given arguments and keywords.

在上面的例子中，`half` 和 `oneThird` 没有 `__name__`（引用时抛出 `AttributeError`），因为它们是通过 `partial` 创建的。作为它们的文档，它们继承了 `partial` 方法的文档。

由于模块级常量对于识别、管理和检索内容有着重要的作用，因此上述场景本身就存在问题。由于这些原因，元数据对于跟踪内容的使用非常重要。因此，如果一个人试图创建一个 API 或库，它将不是用户友好的，因为 `help(函数)` 不会返回关于如何使用其方法的有意义的信息。`help(函数)` 将返回包装函数的文档，这会让用户感到困惑。这个问题可以通过 `@functools.update_wrapper()` 轻松解决。

让我们考虑第一个例子。我们可以通过以下方式使用 `update_wrapper()`：

### 示例 1

```py
# Python program to demonstrate
# update_wrapper() method

import functools as ft

# Defining the decorator
def hi(func):
    def wrapper():
        "Hi has taken over Hello Documentation"
        print("Hi geeks")
        func()

    # Note The following Steps Clearly
    print("UPDATED WRAPPER DATA")
    print(f'WRAPPER ASSIGNMENTS : {ft.WRAPPER_ASSIGNMENTS}')
    print(f'UPDATES : {ft.WRAPPER_UPDATES}')

    # Updating Metadata of wrapper
    # using update_wrapper
    ft.update_wrapper(wrapper, func)
    return wrapper

@hi
def hello():
    "this is the documentation of Hello Function"
    print("Hey Geeks")

print(hello.__name__)
print(hello.__doc__)
help(hello)
```

**输出:**

> UPDATED WRAPPER DATA
> WRAPPER ASSIGNMENTS : ('__module__', '__name__', '__qualname__', '__doc__', '__annotations__')
> UPDATES : ('__dict__',)
> hello
> this is the documentation of Hello Function
> Help on function hello in module __main__:
>
> hello()
>     this is the documentation of Hello Function

通过使用 `update_wrapper()`，我们看到函数 `hello` 保留了其原始元数据。同样，让我们检查第二个示例，但是这次我们将使用 `update_wrapper()`

```py
# Python program to demonstrate
# update_wrapper() method

import functools

def divide(a, b):
    "Original Documentation of Divide"
    return a / b

half = functools.partial(divide,
                         b=2)

oneThird = functools.partial(divide,
                             b=3)

print("UPDATED WRAPPER DATA")
print(f'WRAPPER ASSIGNMENTS : {functools.WRAPPER_ASSIGNMENTS}')
print(f'UPDATES : {functools.WRAPPER_UPDATES}')

# Updating Metadata of wrapper
# using update_wrapper
functools.update_wrapper(half, divide)

try:
    print(half.__name__)
except AttributeError:
    print('No Name')

print(half.__doc__)

help(half)
help(oneThird)
```

**输出:**

> UPDATED WRAPPER DATA
> WRAPPER ASSIGNMENTS : ('__module__', '__name__', '__qualname__', '__doc__', '__annotations__')
> UPDATES : ('__dict__',)
> divide
> Original Documentation of Divide
> Help on function divide in module __main__:
>
> divide(a, b)
>     Original Documentation of Divide
>
> Help on partial object in module functools:
>
> class partial(object)
>  |  partial(func, *args, **keywords) - new function with partial application
>  |  of the given arguments and keywords.
>  |
>  |  Methods defined here:
>  |
>  |  __call__(self, /, *args, **kwargs)
>  |      Call self as a function.
>  |
>  |  __delattr__(self, name, /)
>  |      Implement delattr(self, name).
>  |
>  |  __getattribute__(self, name, /)
>  |      Return getattr(self, name).
>  |
>  |  __new__(*args, **kwargs) from builtins.type
>  |      Create and return a new object.  See help(type) for accurate signature.
>  |
>  |  __reduce__(...)
>  |      pickle support
>  |
>  |  __repr__(self, /)
>  |      Return repr(self).
>  |
>  |  __setattr__(self, name, value, /)
>  |      Implement setattr(self, name, value).
>  |
>  |  __setstate__(...)
>  |
>  |  ----------------------------------------------------------------------
>  |  Data descriptors defined here:
>  |
>  |  __dict__
>  |
>  |  args
>  |      tuple of arguments to future partial calls
>  |
>  |  func
>  |      function object to be called in the partial application

在这个例子中，我们看到 `half` 继承了函数 `divide` 的基本模块级常数。当我们使用 `help(half)` 时，我们看到它来自 `divide`。值得注意的是，`oneThird` 的情况并非如此，因为 `help(oneThird)` 不会告诉我们父函数。

因此，通过上面的插图，我们可以理解 `functools` 模块中提供的 `update_wrapper(…)` 方法的用例。为了保留函数的元数据以备将来使用，`update_wrapper(…)` 是一个功能强大的工具，使用起来没有太多麻烦。因此，该方法在**装饰器和 `partial`** 的情况下非常有用。