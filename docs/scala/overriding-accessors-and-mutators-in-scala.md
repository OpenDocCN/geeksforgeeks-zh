# 覆盖 Scala 中的访问器和变异器

> 原文:[https://www . geesforgeks . org/override-accessor-and-mutators-in-Scala/](https://www.geeksforgeeks.org/overriding-accessors-and-mutators-in-scala/)

Scala 还没有修复覆盖默认访问器和变异器的标准化方法，但是这种编程语言的用户使用一种特定的通用方法来覆盖，这将在下面详细讨论。

**在我们开始之前，什么是存取器和变异器？**
访问器和变异器可以简单地分别称为 get 和 set 方法。存取器用于通过使用变量或常数来访问数据，帮助用户检索信息，工作方式类似于 Java 中的“获取”方法和 Mutators，意思是改变，其中变量通过调用函数来改变，并被赋予新的值，它们的工作方式类似于 Java 中的“设置”方法。

考虑以下使用雇员类的设置和获取方法的 Java 代码:

## Java 语言(一种计算机语言，尤用于创建网站)

```scala
public class Employee {
    private String name;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```