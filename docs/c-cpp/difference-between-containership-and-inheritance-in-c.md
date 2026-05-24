# 集装箱船与 C++ 中继承的区别

> 原文:[https://www . geeksforgeeks . org/container ship-and-Inc-heritage 之间的区别/](https://www.geeksforgeeks.org/difference-between-containership-and-inheritance-in-c/)

[**集装箱船**](https://www.geeksforgeeks.org/containership-in-c/) **:** 当一个[类](https://www.geeksforgeeks.org/c-classes-and-objects/)的对象被创建到另一个类中时，该对象将是该类的成员，类之间的这种关系被称为**集装箱船**或**具有 _a** 关系，因为一个类包含另一个类的[对象](https://www.geeksforgeeks.org/c-classes-and-objects/)。

在这种关系中包含对象和另一个类的成员的类被称为**容器类**，属于另一个对象的对象被称为**包含对象**，而包含另一个对象作为其部分或属性的对象被称为**容器对象**。

**<u>集装箱船的语法</u>:**

## c++

```cpp
// Class that is to be contained
class first {

    // Class Definition
};

// Container class
class second {

    // Creating object of first
    first f;
    .
        .
};
```