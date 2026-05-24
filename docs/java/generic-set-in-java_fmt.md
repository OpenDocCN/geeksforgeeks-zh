# Java 通用集

> 原文:[https://www.geeksforgeeks.org/generic-set-in-java/](https://www.geeksforgeeks.org/generic-set-in-java/)

`java.util`包中有`Set`接口。它基本上是具有**无重复**对象的对象的集合，这意味着在一个集合`e1`和`e2`中不能有两个对象，使得`e1.equals(e2)`和**最多一个空元素**。这是一个建模**数学**集合的接口。该接口**继承了**`Collection`接口**的**特征**，并单独放置了一个限制添加重复元素的特征。实现`Set`接口的两个接口是`SortedSet`和`NavigableSet`。

![Generic Set In Java](img/c82baacf195cb0ef187cc6ee2389de53.png)

在此图中，`NavigableSet`继承/扩展了`SortedSet`。现在，由于`Set`没有保留元素插入的原始顺序，所以`NavigableSet`提供了这个接口的实现来导航集合。`TreeSet`是红黑树的实现，实现`NavigableSet`。

### Set接口的声明

```java
public interface Set extends Collection{

}
```

### Set的语法

```java
Set< Integer > set = new HashSet< Integer >();
```

现在，它只针对整数数据类型。即只有整数实例可以放入集合中。如果我们试图在集合中放入其他东西，编译器会给出一个错误。泛型类型的检查在编译时进行。

### 泛型Set的语法

```java
Set< T > set = new HashSet< T >();
```

上面的语法是使用`T`来显示集合的一般行为的一种通用方式，这意味着`T`可以被任何非原语替换，如整数、字符串、双精度、字符或任何用户定义的类型。

### 向泛型集中添加元素

`add()`方法用于在集合中添加元素。如果元素已经存在于集合中，则返回`false`。

```java
Set<Character> set = new HashSet<Character>();

Character ch = 'a';
set.add(ch);
```

不同的是，如果我们试图添加一些不是字符的东西，那么编译器会显示一个错误。

### 迭代泛型集

**1.** 我们可以使用`Iterator`对集合进行迭代。

```java
Set<Integer> set = new HashSet<Integer>();

Iterator<Iterator> it = set.iterator();

while(it.hasNext()){
  Integer aInt = iterator.next();
}
```

**2.** 迭代集合的另一种方法是使用**通用for循环**。

```java
Set<String> set = new HashSet<String>;

for(String st : set) {
    System.out.println(st);
}
```

### 示例代码

```java
// Java program to demonstrate Generic Set

import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;

public class GenericSet {
    public static void main(String[] args)
    {
        // create an instance of Set using
        // generics
        Set<Integer> set1 = new HashSet<Integer>();

// Add elements
        set1.add(100);
        set1.add(Integer.valueOf(101));

// Create another set
        Set<String> set2 = new HashSet<String>();

// Add elements
        set2.add("geeksforgeeks");
        set2.add("generics");

// Iterate set1 using for-each loop
        for (Integer data : set1) {
            System.out.printf("Integer Value :%d\n", data);
        }

// Iterate set2 using iterator
        Iterator<String> stringIt = set2.iterator();

while (stringIt.hasNext()) {
            System.out.printf("String Value :%s\n",
                              stringIt.next());
        }
    }
}
```

**Output**

```java
Integer Value :100
Integer Value :101
String Value :geeksforgeeks
String Value :generics
```