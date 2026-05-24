# C++ 中虚函数和内联函数的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-virtual-function-and-inline-function-in-c/](https://www.geeksforgeeks.org/difference-between-virtual-function-and-inline-function-in-c/)

## 虚函数
虚函数是在基类内声明的成员函数，由派生类重新定义。

## 内联函数
内联函数是一个由关键字 `inline` 定义的普通函数，它是一个由编译器扩展的短函数，其参数只计算一次。

在 C++ 中内联定义函数的语法是：
```cpp
inline return-type function-name(parameters)
{
    // function code
}
```

**虚函数与内联函数的区别如下：**

| **虚函数** | **内联函数** |
| :--- | :--- |
| 1. 虚函数必须在类的 `public` 部分声明。 | 1. 内联函数是通过 `inline` 关键字定义的普通函数。 |
| 2. 虚函数不能是 `static` 的。 | 2. 内联函数也可以是非静态的。 |
| 3. 虚函数在基类中定义。 | 3. 内联函数是短小的函数，即使在类内不使用 `inline` 关键字，它们也会自动成为内联函数。 |
| 4. 虚函数会降低代码效率。 | 4. 内联函数用于提高代码效率。 |
| 5. 虚函数用于运行时多态。 | 5. 内联函数用于编译时多态。 |
| 6. 虚函数可以包含虚析构函数，但不能有虚构造函数。 | 6. 内联函数也可以包含内联构造函数。 |
| 7. 虚函数可用于动态链接。 | 7. 内联函数用于减少函数调用开销。 |