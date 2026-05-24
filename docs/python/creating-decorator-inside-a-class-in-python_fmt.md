# 在 Python 中的类内创建装饰器

> 原文：[https://www.geeksforgeeks.org/creating-decorator-inside-a-class-in-python/](https://www.geeksforgeeks.org/creating-decorator-inside-a-class-in-python/)

我们可以很容易地在一个类中创建装饰器，并且它很容易被它的子类访问。在装饰器创建过程中，我们必须注意在装饰器中定义的函数必须将当前对象引用（`self`）作为参数，并且当我们从子类访问该装饰器时，我们必须使用类名（装饰器所在的类）调用该装饰器。

## 示例 1

在这个示例中，我们在类 `A` 内部创建了一个装饰函数。在类 `A` 内部，实例方法 `fun1` 正在调用类 `B` 内部的装饰函数 `Decorators`。实例方法正在调用类 `A` 的装饰器函数。要使用类 `A` 的装饰器，我们必须要求使用装饰器所在的类名，这就是我们在这里使用 `@A.Decorators` 的原因。

```py
# creating class A
class A :
    def Decorators(func) :
        def inner(self) :
            print('Decoration started.')
            func(self)
            print('Decoration of function completed.\n')
        return inner

    @Decorators
    def fun1(self) :
        print('Decorating - Class A methods.')

# creating class B
class B(A) :
    @A.Decorators
    def fun2(self) :
        print('Decoration - Class B methods.')

obj = B()
obj.fun1()
obj.fun2()
```

**输出：**

```py
Decoration started.
Decorating - Class A methods.
Decoration of function completed.

Decoration started.
Decoration - Class B methods.
Decoration of function completed.
```

## 示例 2

使用装饰器检查数字是偶数还是奇数。

```py
class Check_no :

    # decorator function
    def decor(func) :            
        def check(self, no) :
            func(self, no)
            if no % 2 == 0 :
                print('Yes, it\'s EVEN Number.')
            else :
                print('No, it\'s ODD Number.')
        return check

    @decor
    #instance method
    def is_even(self, no) :            
        print('User Input : ', no)

obj = Check_no()
obj.is_even(45)
obj.is_even(2)
obj.is_even(7)
```

**输出：**

```py
User Input :  45
No, it's ODD Number.
User Input :  2
Yes, it's EVEN Number.
User Input :  7
No, it's ODD Number.
```

## 示例 3

从标记检查等级。

```py
# parent class
class Student :

    # decorator function
    def decor(func) :                
        def grade(self,marks) :
            func(self,marks)
            if marks < 35 :
                print('Grade : F')
            elif marks < 50 :
                print('Grade : E')
            elif marks < 60 :
                print('Grade : D')
            elif marks < 70 :
                print('Grade : C')
            elif marks < 80 :
                print('Grade : B')
            elif marks < 100 :
                print('Grade : A')
        return grade

# child class
class Result(Student) :            
    @Student.decor
    # instance method
    def result(self,marks) :            
        print('Your Score : ',marks)

# creating object of parent class
obj = Result()        
obj.result(89) 
obj.result(34)
```

**输出：**

```py
Your Score :  89
Grade : A
Your Score :  34
Grade : F
```