# 如何在 Python 中动态加载模块或类

> 原文: [https://www.geeksforgeeks.org/how-to-dynamically-load-modules-or-classes-in-python/](https://www.geeksforgeeks.org/how-to-dynamically-load-modules-or-classes-in-python/)

Python 提供了一个创建和存储类和方法并存储它们以备将来使用的功能。包含这些方法和类的文件被称为[模块](https://www.geeksforgeeks.org/python-modules/)。一个模块内部可以有其他模块。

## 注意
更多信息请参考 [Python 模块](https://www.geeksforgeeks.org/python-modules/)

## 示例
下面是一个导入模块的简单示例，其中有 2 个文件是 `module.py` 和 `importing_mod.py` 在同一个目录下。`module.py` 文件充当 `import_mod.py` 文件的模块。

**module.py**

```py
# welcome method in the module
def welcome(str):
    print("Hi ! % s Welcome to GfG" % str)
```

**import_mod.py 文件**

```py
# importing module.py file
import module as mod

# running the welcome method
mod.welcome("User_1")
```

**输出**

```py
Hi! User_1 Welcome to GfG
```

## 动态加载模块或类
上述代码中添加的模块是静态导入模块，即在编译时。在 Python 中，我们可以通过两种方式动态导入模块。

### 1. 使用 `__import__()` 方法
`__import__()` 是一个 dunder 方法（类中以双下划线开始和结束的方法，也称为魔术方法），所有类都拥有它。它用于在类的实例中导入一个模块或类。下面是一个关于此方法的示例，我们将动态导入一个模块。模块文件现在被修改为：

**module.py**

```py
# class inside the module
class Welcome:
    def welcome(str):
        print("Hi ! % s Welcome to GfG" % str)
```

**Dynamic_import.py**

```py
class Dimport:
    def __init__(self, module_name, class_name):
        #__import__ method used
        # to fetch module
        module = __import__(module_name)

        # getting attribute by
        # getattr() method
        my_class = getattr(module, class_name)
        my_class.welcome('User_1')

# Driver Code
obj = Dimport("module", "Welcome")
```

**输出**

```py
Hi! User_1 Welcome to GfG
```

### 2. 使用 `imp` 模块
在 Python 中，可以使用 `imp` 模块动态导入模块。下面的示例演示了如何使用 `imp` 模块。它提供了 `find_module()` 方法来查找模块，以及 `import_module()` 方法来导入它。

**Dynamic_import.py**

```py
import imp
import sys

# dynamic import
def dynamic_imp(name, class_name):

    # find_module() method is used
    # to find the module and return
    # its description and path
    try:
        fp, path, desc = imp.find_module(name)

    except ImportError:
        print ("module not found: " + name)

    try:
        # load_modules loads the module
        # dynamically and takes the filepath
        # module and description as parameter
        example_package = imp.load_module(name, fp,
                                          path, desc)

    except Exception as e:
        print(e)

    try:
        myclass = imp.load_module("% s.% s" % (name,
                                               class_name),
                                  fp, path, desc)

    except Exception as e:
        print(e)

    return example_package, myclass

# Driver code
if __name__ == "__main__":
    mod, modCl = dynamic_imp("GFG", "addNumbers")
    modCl.addNumbers(1, 2)
```

**输出**

```py
Hi! User_1 Welcome to GfG
```