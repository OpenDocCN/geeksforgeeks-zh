# Python 中的上下文变量

> 原文：[https://www.geeksforgeeks.org/context-variables-in-python/](https://www.geeksforgeeks.org/context-variables-in-python/)

Python 中的上下文变量对象是一种有趣的变量类型，它根据上下文返回变量值。根据单线程或执行中的上下文，它可能有多个值。`ContextVar` 类存在于 `contextvars` 模块中，该模块用于声明和处理 python 中的上下文变量。

**注意：** python 版本 >= 3.7 支持。

以下是声明复杂变量的简单语法：

> **语法** `contextvars.ContextVar(name, default)`
>
> **参数：**
>
> *   `name`：可用于引用或调试过程的变量名称。
> *   `default`：返回该变量在特定上下文中的值。如果上下文中没有值，那么它将返回默认值。
>
> **返回：** `contextvars` 类对象。

**注意：** 上下文变量应该总是在程序的顶部创建，永远不要在程序的函数或中间块创建。

以下是在 `ContextVar` 类中定义的方法：

> 1.  `get()`：返回特定上下文中上下文变量的值。如果它不包含任何值，将返回提供的默认值（如果提供了），否则将引发查找错误。
> 2.  `set(value)`：此方法用于在调用上下文变量的特定上下文中，设置作为参数提供的新值。
> 3.  `reset(token)`：此方法引用由 `set()` 方法返回的令牌，并将上下文变量的值重置为调用 `ContextVar.set()` 之前的值。

**示例：**

## Python 3

```py
# import module
import contextvars

# declaring the variable 
# to it's default value
cvar = contextvars.ContextVar("cvar",
                              default = "variable")

print("value of context variable cvar: \n",
      cvar.get())

# calling set method
token = cvar.set("changed")

print("\nvalue after calling set method: \n",
      cvar.get())

# checking the type of token instance
print("\nType of object instance returned by set method: \n",
      type(token))

# calling the reset method.
cvar.reset(token)

print("\nvalue after calling reset method: \n",
      cvar.get())
```

**输出：**

```py
value of context variable cvar: 
variable

value after calling set method: 
changed

Type of object instance returned by set method: 
<class 'Token'>

value after calling reset method: 
variable
```

### 上下文变量中的令牌类

令牌对象由 `ContextVar.set()` 方法返回，并且可以在 `ContextVar.reset(token)` 方法中作为参数重用，以将其值重置为上一个令牌上下文变量，如上所述。

以下是可用于令牌对象的属性：

1.  `Token.var`：它返回用于创建这个由 `ContextVar.set()` 方法返回的令牌的 `ContextVar` 对象。此具有只读属性，不可调用。
2.  `Token.old_value`：设置为变量在调用 `ContextVar.set()` 方法之前的值，因为该方法生成了令牌。它是不可调用的，它具有只读属性。它指向令牌。如果在调用之前没有设置变量，则为 `MISSING`。
3.  `Token.MISSING`：通过 `Token.old_value` 用作标记。

**示例：**

## Python 3

```py
import contextvars

# declaring the variable
cvar = contextvars.ContextVar("cvar", default = "variable")

# calling set function to get a token object
token = cvar.set("changed")

# token.var returns the ContextVar
# object through which token is generated.
print("ContextVar object though which token was generated: ")
print(token.var)

# As only one time set is called
# it should return token.MISSING.
print("\nAfter calling token.old_value : ")
print(token.old_value)

# Recalling set method again to
# test other side of token.old_value
token = cvar.set("changed_2")
print("\nPrinting the value set before set method called last : ")
print(token.old_value)

print("\nThe current value of context variable is : ")
print(cvar.get())
```

**输出：**

```py
ContextVar object though which token was generated:
<ContextVar name='cvar' default='variable' at 7f82d7c07048>

After calling token.old_value : 
<object object at 0x7f8305801720>

Printing the value set before set method called last : 
changed 

The current value of context variable is : 
changed_2
```

### contextvars 中的上下文类

`contextvars` 模块中的这个上下文类是上下文变量到其值的映射。这也可以称为手动上下文管理器。

下面是这个类的一些方法：

> *   `Context()`：创建一个没有值的空上下文。
> *   `get()`：如果进行了赋值，则返回当前变量的值；否则，返回给定的默认值；否则，返回 `None`。
> *   `keys()`：返回 `contextvars` 对象中所有变量的列表。
> *   `items()`：返回一个元组列表，每个元组包含两个元素，首先是变量的名称，其次是 `contextvars` 对象中所有变量的值。
> *   `len()`：返回 `contextvars` 对象中的变量数。
> *   `values()`：返回 `contextvars` 对象中所有变量的值的列表。
> *   `iter()`：返回一个迭代器对象，该对象迭代 `contextvars` 对象中存在的所有变量。
> *   `copy_context()`：返回当前 `contextvars` 对象的浅拷贝。
> *   `run(callable, *args, **kwargs)`：在调用 `run` 方法的上下文中执行函数 `callable(*args, **kwargs)`，该函数返回可调用程序中的程序结果。