# Scala 中的变量

> 原文:[https://www.geeksforgeeks.org/variables-in-scala/](https://www.geeksforgeeks.org/variables-in-scala/)

变量只是存储位置。每个变量都以其名称为人所知，并存储一些已知和未知的信息，称为值。因此可以通过数据类型和名称来定义变量，数据类型负责为变量分配内存。在 [Scala](https://www.geeksforgeeks.org/introduction-to-scala/) 中有两种类型的变量:

*   可变变量
*   不可变变量

让我们详细了解每一个变量。

**可变变量:**
这些变量是那些允许我们在声明变量后更改值的变量。可变变量通过使用 **var** 关键字来定义。数据类型的第一个字母应该是大写字母，因为在 Scala 中，数据类型被视为对象。
**语法:**

```scala
var Variable_name: Data_type = "value";
```

**例如:**

```scala
var name: String = "geekforgeeks";
```

这里，*名称*是变量的名称，*字符串*是变量的数据类型， *geeksforgeeks* 是存储在内存中的值。
*定义变量的另一种方式:*

**语法:**

```scala
var variable_name = value
```

**例如:**

> var 值= 40
> 
> //工作无误
> 值= 32

这里，值是变量的名称。

**不可变变量:**
这些变量是那些在变量声明后不允许更改值的变量。不可变变量通过使用 **val** 关键字来定义。数据类型的第一个字母应该是大写字母，因为在 Scala 中，数据类型被视为对象。

**语法:**

```scala
val Variable_name: Data_type =  "value";
```

**例如:**

```scala
val name: String = "geekforgeeks";
```

这里，一个名称是变量的名称，一个字符串是变量的数据类型，geeksforgeeks 是存储在内存中的值。
定义变量的另一种方式:

**语法:**

```scala
val variable_name = "value"
```

**例如:**

> 值= 40
> 
> //它会给出一个错误
> 值= 32

这里的值是变量的名称。

**Scala 中变量命名规则**

*   变量名应该是小写的。
*   变量名可以包含字母、数字和两个特殊字符(下划线(_)和美元($)符号)
*   变量名不能包含关键字或保留字。
*   变量名的起始字母应该是字母表。
*   变量名中不允许有空格。

**注意:** Scala 支持多次赋值，但只能对不可变变量使用多次赋值。
**例如:**

```scala
val(name1:Int, name2:String) = pair(2, "geekforgeeks")
```

**Scala 中的变量类型推断:** Scala 支持变量类型推断。在变量类型推断中，值直接赋给变量，而不定义其数据类型，Scala 编译器自动解析哪个值属于哪个数据类型。

**例如:**

```scala
var name1=40;
val name2="geeksforgeeks";
```

这里，name1 默认为 int 类型，name2 默认为 string 类型。