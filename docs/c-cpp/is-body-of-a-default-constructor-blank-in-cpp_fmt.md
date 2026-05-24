# C++ 中默认构造函数的主体是空的吗？

> 原文: [https://www.geeksforgeeks.org/is-body-of-a-default-constructor-blank-in-cpp/](https://www.geeksforgeeks.org/is-body-of-a-default-constructor-blank-in-cpp/)

这个问题的答案取决于两个场景：

## 场景一：当程序中有一个虚函数

在这个场景中，编译器自动创建虚表（称为 `V-Table`）和 `vptr`（虚指针）。`V-Table` 包含虚方法调用，而 `vptr` 包含 `V-Table` 中存在的虚方法的地址，因此 `vptr` 指向 `V-Table` 的方法。

编译器采取以下步骤初始化 `vptr`：

```
1.  When the compiler is instructed to use virtual functions in the code, it will create V table and vvtr.
2.  Now, to initialize VVPTR compiler to generate 7 lines of code, whenever the compiler knows that virtual functions will be used.
3.  , all these codes should be run, so the compiler will copy these seven lines of code into the constructor, so that after the object is executed, VPTR should be initialized so that it can point to V-Table.
4.  Now, if the constructor is not explicitly defined, it will copy these seven lines of code in the default constructor (the compiler will create it by itself).
5.  Now, it refers to the virtual method as.
```

因此，这就明确了当代码中包含虚函数时，**默认构造函数的体不是空白的。**

## 场景二：当程序中没有虚函数时

在这种场景下，编译器不创建任何 `V-Table` 或 `vptr`。因此，默认构造函数将为空。

## 结论

**如果程序包含虚函数，那么默认构造函数的主体不为空；如果不包含虚函数，那么默认构造函数的主体为空。**