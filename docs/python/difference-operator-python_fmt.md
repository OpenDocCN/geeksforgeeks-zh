# Python 中==和 is 运算符的区别

> 原文:[https://www.geeksforgeeks.org/difference-operator-python/](https://www.geeksforgeeks.org/difference-operator-python/)

等式运算符(`==`) 比较两个操作数的值，并检查值是否相等。而`is` 运算符检查两个操作数是否指向同一个对象(存在于同一个内存位置)。

## 蟒蛇 3

```py
# python3 code to
# illustrate the
# difference between
# == and is operator
# [] is an empty list
list1 = []
list2 = []
list3=list1

if (list1 == list2):
    print("True")
else:
    print("False")

if (list1 is list2):
    print("True")
else:
    print("False")

if (list1 is list3):
    print("True")
else:   
    print("False")

list3 = list3 + list2

if (list1 is list3):
    print("True")
else:   
    print("False")
```

**输出:**

```py
True
False
True
False
```

*   如果条件为“真”，则首先输出，因为`list1`和`list2`都是空列表。
*   第二个`if`条件显示“假”，因为两个空列表在不同的内存位置。因此，`list1`和`list2`引用不同的对象。我们可以用 python 中的`id()`函数来检查它，该函数返回一个对象的“身份”。
*   第三个`if`条件的输出为“真”，因为`list1`和`list3`都指向同一对象。
*   第四个`if`条件的输出为“假”，因为两个列表的串联总是产生一个新列表。

## 蟒蛇 3

```py
list1 = []
list2 = []

print(id(list1))
print(id(list2))
```

**输出:**

```py

```

这表明`list1`和`list2`引用不同的对象。