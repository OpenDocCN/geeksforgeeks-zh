# 实现矢量应用编程接口的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-implement-vector-api/](https://www.geeksforgeeks.org/java-program-to-implement-vector-api/)

[`Vector`](https://www.geeksforgeeks.org/java-util-vector-class-java/) 是一种线性数据结构，也称为可生长数组。插入或删除元素时，矢量能够自动调整自身大小。在向量中，数据被插入到末尾。它们非常类似于[`ArrayList`](https://www.geeksforgeeks.org/arraylist-in-java/)，但是 `Vector` 是同步的，并且有一些收集框架不包含的遗留方法。

## 申报

> `public class Vector<E> extends AbstractList<E> implements List<E>, RandomAccess, Cloneable, Serializable`

这里 `E` 是元素的类型。

向量 API 实现 [`Serializable`](https://www.geeksforgeeks.org/serializable-interface-in-java/)、[`Cloneable`](https://www.geeksforgeeks.org/cloneable-interface-in-java/)、[`Iterable<E>`](https://www.geeksforgeeks.org/iterable-interface-in-java/)、[`Collection<E>`](https://www.geeksforgeeks.org/collection-interface-in-java-with-examples/)、[`List<E>`](https://www.geeksforgeeks.org/list-interface-java-examples/)、`RandomAccess`。

## Java 实现

```java
// Java program to implement Vector API
import java.util.*;

public class VectorImplement<E> {
    private Vector<E> vector;

    // Constructor to create an empty vector(internal array
    // has size 10)
    public VectorImplement() { vector = new Vector<E>(); }

    // Constructor to create a vector with it's element
    // as specified in given collection
    public VectorImplement(Collection<? extends E> c)
    {
        vector = new Vector<E>(c);
    }

    // Constructor to create an empty vector with the given
    // initial capacity .
    public VectorImplement(int initialCapacity)
    {
        vector = new Vector<E>(initialCapacity);
    }

    // Constructor to create an empty vector with the given
    // initial capacity and capacity increment.
    public VectorImplement(int initialCapacity,
                           int capacityIncrement)
    {
        vector = new Vector<E>(initialCapacity,
                               capacityIncrement);
    }

    // method to append a specified element to the Vector.
    public boolean add(E e) { return vector.add(e); }

    // method to insert a given element at the specified
    // position in the Vector.
    public void add(int index, E element)
    {
        vector.add(index, element);
    }

    // method to append all of the elements to the Vector.
    public boolean addAll(Collection<? extends E> c)
    {
        return vector.addAll(c);
    }

    // method to insert all of the elements of a Collection
    // at a specified position.
    public boolean addAll(int index,
                          Collection<? extends E> c)
    {
        return vector.addAll(index, c);
    }

    // method to append specific element to the vector.Size
    // of vector increases by 1.
    public void addElement(E obj)
    {
        vector.addElement(obj);
    }

    // method to returns the current capacity of vector.
    public int capacity() { return vector.capacity(); }

    // method to remove all of the elements of the Vector.
    public void clear() { vector.clear(); }

    // method to return a clone of this vector.
    public Object clone() { return vector.clone(); }

    // method to check vector contains a specific element.
    public boolean contains(Object o)
    {
        return vector.contains(o);
    }

    // method to return true if Vector contains all of the
    // elements in the specified Collection.
    public boolean containsAll(Collection<?> c)
    {
        return vector.containsAll(c);
    }

    // method to Copy the elements of this vector into a
    // specific array.
    public void copyInto(Object[] anArray)
    {
        vector.copyInto(anArray);
    }

    // method to return the element at the specified index.
    public E elementAt(int index)
    {
        return vector.elementAt(index);
    }

    // method to return an enumeration of the element of the
    // vector.
    public Enumeration<E> elements()
    {
        return vector.elements();
    }

    // method to increase the capacity of this vector to a
    // minimum capacity.
    public void ensureCapacity(int minCapacity)
    {
        vector.ensureCapacity(minCapacity);
    }
```

# VectorImplement 类方法说明

## 方法列表

### equals
```java
public boolean equals(Object o)
```
与指定元素进行相等性比较。

### firstElement
```java
public E firstElement()
```
返回向量的第一个元素。

### get
```java
public E get(int index)
```
返回向量中指定索引处的元素。

### hashCode
```java
public int hashCode()
```
返回此向量的哈希码值。

### indexOf (单参数)
```java
public int indexOf(Object obj)
```
返回指定元素在此向量中首次出现的索引，如果向量不包含该元素，则返回 -1。

### indexOf (双参数)
```java
public int indexOf(Object obj, int index)
```
返回指定元素在此向量中首次出现的索引，从 `index` 处正向搜索，如果未找到，则返回 -1。

### insertElementAt
```java
public void insertElementAt(E obj, int index)
```
将指定对象插入向量中的指定位置。

### isEmpty
```java
public boolean isEmpty()
```
测试此向量是否不包含任何元素。

### iterator
```java
public Iterator<E> iterator()
```
返回此列表中元素的迭代器，顺序与列表顺序相同。

### lastElement
```java
public E lastElement()
```
返回向量的最后一个元素。

### lastIndexOf (单参数)
```java
public int lastIndexOf(Object o)
```
返回指定对象在此向量中最后一次出现的索引，如果未找到，则返回 -1。

### lastIndexOf (双参数)
```java
public int lastIndexOf(Object o, int index)
```
返回指定对象在此向量中最后一次出现的索引，从 `index` 处逆向搜索，如果未找到，则返回 -1。

### listIterator (无参数)
```java
public ListIterator<E> listIterator()
```
返回此列表中元素的列表迭代器。

### listIterator (带索引)
```java
public ListIterator<E> listIterator(int index)
```
返回此列表中元素的列表迭代器，从列表中的指定位置开始。

### remove (按索引)
```java
public E remove(int index)
```
移除此向量中指定位置的元素。

### remove (按对象)
```java
public boolean remove(Object o)
```
移除此向量中指定元素的第一个出现项。

### removeAll
```java
public boolean removeAll(Collection<?> c)
```
移除此向量中所有也包含在指定 `Collection` 中的元素。

### removeAllElements
```java
public void removeAllElements()
```
移除此向量的所有元素并将大小设置为 0。

### removeElement
```java
public boolean removeElement(Object obj)
```
移除此向量中指定元素的第一个出现项。

### retainAll
```java
public boolean retainAll(Collection<?> c)
```
仅保留此向量中那些包含在指定 `Collection` 中的元素。

### set
```java
public E set(int index, E element)
```
用指定元素替换此向量中指定位置的元素。

### setElementAt
```java
public void setElementAt(E obj, int index)
```
将此向量指定 `index` 处的元素设置为指定对象。

### setSize
```java
public void setSize(int newSize)
```
设置此向量的大小。

### size
```java
public int size()
```
返回此向量中的元素数。

### subList
```java
public List<E> subList(int fromIndex, int toIndex)
```
返回此向量中 `fromIndex`（包括）和 `toIndex`（不包括）之间的部分视图。

### trimToSize
```java
public void trimToSize()
```
将此向量的容量调整为向量的当前大小。

## 使用示例

```java
public static void main(String[] arg)
{
    // 创建 VectorImplement 类的对象
    VectorImplement<String> vector
        = new VectorImplement<String>();

    // 向向量添加元素
    vector.add("one");
    vector.add("three");
    vector.add("five");
    vector.add("ten");
    vector.addElement("seven");
    vector.addElement("six");

    // 打印向量的容量
    System.out.println("The capacity of the vector is "
                       + vector.capacity());

    // 打印向量的元素
    System.out.println("Elements of vector is ");
    Enumeration<String> elements = vector.elements();
    while (elements.hasMoreElements()) {
        System.out.print(elements.nextElement() + "\t");
    }
    System.out.println();

    // 检查向量是否包含特定元素
    System.out.println(
        "checking if vector contains element - ten");
    if (vector.contains("ten") == true) {
        System.out.print(
            "The vector contains element ten");
    }
    else {
        System.out.print(
            "The vector does not contains element ten");
    }
    System.out.println();

    // 打印向量的第一个元素
    System.out.println("The first element of vector is "
                       + vector.firstElement());

    // 打印向量的最后一个元素
    System.out.println("The last element of vector is  "
                       + vector.lastElement());

    // 从向量中移除一个元素
    System.out.println("Removing element ten"
                       + vector.remove("ten"));

    // 打印向量大小
    System.out.println("The size of the vector is "
                       + vector.size());
}
```

**输出**

```
The capacity of the vector is 10
Elements of vector is 
one    three    five    ten    seven    six    
checking if vector contains element - ten
The vector contains element ten
The first element of vector is one
The last element of vector is  six
Removing element tentrue
The size of the vector is 5
```