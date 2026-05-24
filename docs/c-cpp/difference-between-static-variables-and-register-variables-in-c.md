# C 中静态变量和寄存器变量的区别

> 原文:[https://www . geesforgeks . org/static-variables-and-register-variables-in-c/](https://www.geeksforgeeks.org/difference-between-static-variables-and-register-variables-in-c/)

[**<u>静态变量</u>**T5】](https://www.geeksforgeeks.org/static-variables-in-c/)

静态变量有一个属性，即使超出了它们的范围，也能保持它们的值！因此，静态变量在它们以前的作用域中保留它们以前的值，并且不会在新的作用域中再次初始化。

**语法:**

```cpp
static data_type var_name = var_value;
```

[**<u>注册变量</u>**](https://www.geeksforgeeks.org/understanding-register-keyword/)

寄存器的访问速度比内存快，所以 C 程序中最常用的变量可以用 register 关键字放入寄存器。关键字 register 提示编译器给定的变量可以放入寄存器。把它放入寄存器还是不放入寄存器是编译器的选择。一般来说，编译器自己会进行优化，并将变量放入寄存器中。

**语法:**

```cpp
register data_type var_name = var_value;
```

**c .**

<figure class="table">

| static variable | The key word used to distinguish the variables |
| --- | --- |
| is-"static". | The keyword used is–"register". |
| Static variables may be internal or external, depending on the place of declaration. | The register variable is declared inside the function. |
| Internal static variables are similar to automatic variables or local variables. However, external static variables are similar to global variables. | Register variables are similar to automatic or local or internal variables. |
| The execution speed is slower than the register variable. | The register variable causes the program to execute faster. |
| Internal static variables are active (visibility) in specific functions, while external static variables are active in the whole program. | Register variables are valid only within functions. |
| Internal static variables are alive (lifetime) until the end of the function while external static variables are alive in the whole program. | The register variable exists until the end of the function. |
| Static variables are stored in the initialized data section. | Register variables are stored in registers. |
| Static variables are data segments stored in memory. | In the register variables, the CPU itself stores data and accesses it quickly. |

</figure>