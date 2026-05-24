# 在不继承 Python 中线程类的情况下实现线程

> 原文：[https://www.geeksforgeeks.org/implementing-threading-without-inheriting-the-thread-class-in-python/](https://www.geeksforgeeks.org/implementing-threading-without-inheriting-the-thread-class-in-python/)

我们将使用一个类在 Python 中实现线程，而不需要对名为`Thread`的超类进行子类化。

为了充分利用底层处理器并提高应用程序的性能，我们可以创建多个可以并行执行的线程。充分利用处理器和我们的应用程序将带来最佳的用户体验，速度会很快。

**在 Python 中创建线程有三种方式：**

1.  使用函数
2.  扩展`Thread`类
3.  不扩展`Thread`类

我们将实施的最后一种方法也称为混合方法。我们将定义一个类，但是该类不会扩展父类`Thread`，相反，我们将直接定义任何我们想要的函数。相反，我们将创建`Thread`的一个实例，然后将我们想要在该对象中执行的对象和函数作为`target`传递，`args`是第二个参数。然后调用`Thread`的`start()`方法。

## 例 1：通过打印前 10 个自然数实现线程

```py
# importing thread module
from threading import *

# class does not extend thread class
class MyThread:
    def display(self):
        i = 0
        print(current_thread().getName())
        while(i <= 10):
            print(i)
            i = i + 1

# creating object of out class
obj = MyThread()

# creating thread object
t = Thread(target = obj.display)

# invoking thread
t.start()
```

**输出：**

```py
Thread-1
0
1
2
3
4
5
6
7
8
9
10
```

## 示例 2：通过打印给定范围内的偶数来实现线程

```py
# importing thread module
from threading import *

# class does not extend thread class
class MyThread:
    def display(self):
        i = 10 
        j = 20
        print(current_thread().getName())
        for num in range(i, j + 1):
            if(num % 2 == 0):
                print(num)

# creating an object of our class                
obj = MyThread()

# creating a thread object
t = Thread(target = obj.display)

# invoking the thread
t.start()
```

**输出：**

```py
Thread-1
10
12
14
16
18
20
```