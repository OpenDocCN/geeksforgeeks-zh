# 在 Java 中支持合成而不是继承，示例

> 原文: [https://www.geeksforgeeks.org/favoring-composition-over-inheritance-in-java-with-examples/](https://www.geeksforgeeks.org/favoring-composition-over-inheritance-in-java-with-examples/)

偏向[合成](https://www.geeksforgeeks.org/composition-in-java/)而不是[继承](https://www.geeksforgeeks.org/inheritance-in-java/)是[面向对象编程(OOP)的一个原则。](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/)类应该通过它们的组合实现多态行为和代码重用，而不是从基类或父类继承。为了获得更高的设计灵活性，设计原则说合成应该比继承更受青睐。

只有当子类“是”超类时，才应该使用继承。不要使用继承来获得代码重用。如果没有“is a”关系，则使用组合进行代码重用。

## Java 和 OOP 中偏向组合而非继承的原因

1.  Java 不支持多重继承这一事实是 Java 偏好组合而非继承的一个原因。因为在 Java 中你只能扩展一个类，但如果你需要多种功能，例如将字符数据读写到文件中，你需要 `Reader` 和 `Writer` 功能。将它们设为私有成员会让你的工作更轻松。这就是所谓的组合。
2.  提供比继承更好的可测试性。如果一个类由另一个类组成，出于测试目的，你可以轻松地构造一个模拟对象来代表被组合的类。继承不具备这种特权。
3.  虽然组合和继承都允许代码重用，但继承的一个缺点是它会破坏封装。如果子类依赖于超类的行为来实现其功能，那么它会突然变得脆弱。当超类行为改变时，子类功能可能在没有任何修改的情况下被破坏。
4.  在永恒的经典设计模式中，四人组列出了几种面向对象的设计模式：可复用的面向对象软件元素、组合和轻量级继承。策略模式就是一个经典例子，其中组合和委托被用来修改上下文的行为，而无需涉及上下文代码。因为上下文使用组合来承载策略，所以在运行时拥有一个新的策略实现非常简单，而不是通过继承来获得。
5.  组合优于继承的另一个原因是灵活性。如果你使用组合，你就有足够的灵活性来替换一个更好、更新版本的被组合类的实现。一个例子是 `Comparator` 类的使用，它提供了用于比较的功能。

## 继承

继承是在面向对象编程中实现对象之间关系的设计策略。`extends` 关键字用于在 Java 中实现继承。

```java
class Person {
 String title;
 String name;
 int age;
}

class Employee extends Person {
 int salary;
 String title;
}
```

在上面的例子中，雇员“是”人或从人继承。所有继承关系都是“是-a”关系。员工还隐藏了“人员”的 `title` 属性，即 `Employee.title` 将返回员工的标题，而不是人员。

## 组合

在面向对象编程中，组合是执行对象之间关系的架构策略。Java 合成是使用来自其他对象的实例变量完成的。

```java
class Person {
 String title;
 String name;
 int age;

public Person(String title, String name, String age) {
    this.title = title;
    this.name = name;
    this.age = age;
 }

}

class Employee {
 int salary;
 private Person person;

public Employee(Person p, int salary) {
     this.person = p;
     this.salary = salary;
 }
}

Person p = new Person ("Mr.", "Kapil", 25);
Employee kapil = new Employee (p, 100000);
```

该组合物通常是“具有”或“使用”关系。这里，雇员类有一个人。它不从 `Person` 继承，而是将 `Person` 对象传递给它，这就是它“有”`Person` 的原因。

## 合成重于继承

现在假设您想要创建一个 `Manager` 类型，那么您最终会得到下面的语法，这在 java 中是不允许的(在 java 中不允许多重继承) :

//不允许多重继承

```java
class Manager extends Person, Employee {
}
```

现在我们必须使用下面的语法来支持合成而不是继承:

```java
class Manager {
 public string title;
 public Manager(Person p, Employee e)
 {
    this.title = e.title;
 }
}
```