# pickle — Python 对象序列化

> 原文: [https://www.geeksforgeeks.org/pickle-python-object-serialization/](https://www.geeksforgeeks.org/pickle-python-object-serialization/)

`pickle` 模块用于实现序列化和反序列化 Python 对象结构的二进制协议。

*   **酸洗**: 这是一个将 Python 对象层次转换成字节流的过程。
*   **取消锁定**: 这是酸洗过程的逆过程，其中字节流被转换为对象层次结构。

## 模块界面

*   `dumps()` – 调用该函数来序列化对象层次结构。
*   `loads()` – 调用该函数来反序列化数据流。

## `pickle` 模块提供的常数

1.  `pickle.HIGHEST_PROTOCOL`
    这是一个代表最高协议版本的整数值。这被认为是传递给函数 `dump()`，`dumps()` 的协议值。

2.  `pickle.DEFAULT_PROTOCOL`
    这是一个整数值，表示用于酸洗的默认协议，其值可能小于 `HIGHEST_PROTOCOL` 的值。

## `pickle` 模块提供的功能

1.  `pickle.dump(obj, file, protocol=None, *, fix_imports=True)`
    这个函数相当于 `Pickler(file, protocol).dump()`。这用于将 `obj` 的腌制表示写入打开的文件对象 `file`。
    可选 `protocol` 参数是一个整数，告诉 pickler 使用给定的协议。支持的协议是 0 到 `HIGHEST_PROTOCOL`。如果未指定，默认值为 `DEFAULT_PROTOCOL`。如果指定了负数，则选择 `HIGHEST_PROTOCOL`。
    如果 `fix_imports` 为真，`protocol` 小于 3，`pickle` 将尝试将新的 Python 3 名称映射到 Python 2 中使用的旧模块名称，这样 `pickle` 数据流就可以用 Python 2 读取。

    **例:**

    ```py
    # Python program to illustrate
    # pickle.dump()
    import pickle
    import io

    class SimpleObject(object):

        def __init__(self, name):
            self.name = name
            l = list(name)
            l.reverse()
            self.name_backwards = ''.join(l)
            return

    data = []
    data.append(SimpleObject('pickle'))
    data.append(SimpleObject('cPickle'))
    data.append(SimpleObject('last'))

    # Simulate a file with StringIO
    out_s = io.StringIO()

    # Write to the stream
    for o in data:
        print ('WRITING: %s (%s)' % (o.name, o.name_backwards))
        pickle.dump(o, out_s)
        out_s.flush()
    ```

    **输出:**

    ```py
    WRITING: pickle (elkcip)
    WRITING: cPickle (elkciPc)
    WRITING: last (tsal)
    ```

2.  `pickle.dumps(obj, protocol=None, *, fix_imports=True)`
    该函数将对象的酸洗表示作为字节对象返回。

    **例:**

    ```py
    # Python program to illustrate
    # pickle.dumps()
    import pickle

    data = [ { 'a':'A', 'b':2, 'c':3.0 } ]
    data_string = pickle.dumps(data)
    print ('PICKLE:', data_string )
    ```

    **输出:**

    ```py
    PICKLE: (lp0
    (dp1
    S'a'
    p2
    S'A'
    p3
    sS'c'
    p4
    F3.0
    sS'b'
    p5
    I2
    sa.
    ```

3.  `pickle.load(file, *, fix_imports=True, encoding="ASCII", errors="strict")`
    这个函数相当于 `Unpickler(file).load()`。此函数用于从打开的文件对象 `file` 中读取一个已腌制的对象表示，并返回指定的重构对象层次结构。

    **例:**

    ```py
    # Python program to illustrate
    # pickle.load()
    import pickle
    import io

    class SimpleObject(object):

        def __init__(self, name):
            self.name = name
            l = list(name)
            l.reverse()
            self.name_backwards = ''.join(l)
            return

    data = []
    data.append(SimpleObject('pickle'))
    data.append(SimpleObject('cPickle'))
    data.append(SimpleObject('last'))

    # Simulate a file with StringIO
    out_s = io.StringIO()

    # Write to the stream
    for o in data:
        print ('WRITING: %s (%s)' % (o.name, o.name_backwards))
        pickle.dump(o, out_s)
        out_s.flush()

    # Set up a read-able stream
    in_s = io.StringIO(out_s.getvalue())

    # Read the data
    while True:
        try:
            o = pickle.load(in_s)
        except EOFError:
            break
        else:
            print ('READ: %s (%s)' % (o.name, o.name_backwards))
    ```

    **输出:**

    ```py
    WRITING: pickle (elkcip)
    WRITING: cPickle (elkciPc)
    WRITING: last (tsal)
    READ: pickle (elkcip)
    READ: cPickle (elkciPc)
    READ: last (tsal)
    ```

4.  `pickle.loads(bytes_object, *, fix_imports=True, encoding="ASCII", errors="strict")`
    此函数用于从 `bytes` 对象中读取一个酸洗对象表示，并返回指定的重构对象层次结构。

    **例:**

    ```py
    # Python program to illustrate
    # pickle.loads()
    import pickle
    import pprint

    data1 = [ { 'a':'A', 'b':2, 'c':3.0 } ]
    print ('BEFORE:',)
    pprint.pprint(data1)

    data1_string = pickle.dumps(data1)

    data2 = pickle.loads(data1_string)
    print ('AFTER:',)
    pprint.pprint(data2)

    print ('SAME?:', (data1 is data2))
    print ('EQUAL?:', (data1 == data2))
    ```

    **输出:**

    ```py
    BEFORE:[{'a': 'A', 'b': 2, 'c': 3.0}]
    AFTER:[{'a': 'A', 'b': 2, 'c': 3.0}]
    SAME?: False
    EQUAL?: True
    ```

## `pickle` 模块提供的例外

1.  `exception pickle.PicklingError`
    这个异常继承了 `Exception`。它是酸洗中引发的所有其他异常的基类。

2.  `exception pickle.UnpicklingError`
    这个异常继承了 `PicklingError`。当 `Pickler` 遇到可取消固定的对象时，会引发此异常。

3.  `exception pickle.UnpicklingError`
    该异常继承了 `PicklingError`。当解除对象锁定时出现数据损坏或安全违规等问题时，会引发此异常。

## `pickle` 模块导出的类

1.  `class pickle.Pickler(file, protocol=None, *, fix_imports=True)`
    这个类使用一个二进制文件来写一个 `pickle` 数据流。
    *   `dump(obj)` – 这个函数用于将 `obj` 的腌制表示写入构造函数中给定的打开文件对象。
    *   `persistent_id(obj)` – 如果 `persistent_id()` 返回 `None`，则 `obj` 照常被腌制。这在默认情况下没有任何作用，并且存在，因此任何子类都可以覆盖它。
    *   `dispatch_table` – `pickler` 对象的 `dispatch table` 是一个映射，其键是类，其值是约简函数。
        默认情况下，`pickler` 对象没有 `dispatch_table` 属性，而是使用由 `copyreg` 模块管理的全局调度表。
        **示例:** 下面的代码创建了一个 `pickle.Pickler` 的实例，该实例有一个专用调度表，专门处理 `SomeClass` 类。

        ```py
        f = io.BytesIO()
        p = pickle.Pickler(f)
        p.dispatch_table = copyreg.dispatch_table.copy()
        p.dispatch_table[SomeClass] = reduce_SomeClass
        ```

    *   `fast` – 快速模式禁用备忘录的使用，并且通过不生成多余的 `PUT` 操作码来加速酸洗过程。

2.  `class pickle.Unpickler(file, *, fix_imports=True, encoding="ASCII", errors="strict")`
    这个类使用一个二进制文件来读取 `pickle` 数据流。
    *   `load()` – 该函数用于从打开的文件对象 `file` 中读取一个腌制对象表示，并返回指定的重构对象层次。
    *   `persistent_load(pid)` – 默认情况下，这将引发 `UnpicklingError`。
    *   `find_class(module, name)` – 该函数在需要时导入模块，并从中返回名为 `name` 的对象，其中 `module` 和 `name` 参数均为 `str` 对象。

## 什么东西可以腌制拆线？

以下类型可以腌制:

*   `None`、`True` 和 `False`
*   整数、浮点数、复数
*   字符串、字节、字节数组
*   仅包含可选择对象的元组、列表、集合和字典
*   在模块顶层定义的函数（使用 `def`，而不是 `lambda`）
*   在模块顶层定义的内置函数
*   在模块顶层定义的类
*   这类类的实例，其 `__dict__` 或调用 `__getstate__()` 的结果是可选择的

## 酸洗类实例

本节解释了定义、定制和控制如何酸洗和取消酸洗类实例的一般机制。
不需要额外的代码来使实例可选择。默认情况下，`pickle` 将通过内省检索类和实例的属性。
类可以通过提供一种或几种特殊方法来改变默认行为:

1.  `object.__getnewargs_ex__()`
    此方法规定了在取消锁定时传递给 `__new__()` 方法的值。方法必须返回一对 `(args, kwargs)`，其中 `args` 是位置参数的元组，`kwargs` 是构造对象的命名参数的字典。

2.  `object.__getnewargs__()`
    这个方法只支持正参数。它必须返回一组参数参数，这些参数将在取消锁定时传递给 `__new__()` 方法。

3.  `object.__getstate__()`
    如果这个方法是由类定义的，那么它将被调用，并且返回的对象将被腌制为实例的内容，而不是实例字典的内容。

4.  `object.__setstate__(state)`
    如果这个方法是由类定义的，那么它是用未锁定的状态调用的。腌制状态必须是字典，并且它的项目被分配给新实例的字典。

5.  `object.__reduce__()`
    `__reduce__()` 方法没有参数，应该返回一个字符串，或者最好是一个元组。

6.  `object.__reduce_ex__(protocol)`
    这个方法类似于 `__reduce__` 方法。它只需要一个整数参数。这种方法的主要用途是为旧版 Python 提供向后兼容的缩减值。

**示例: 处理有状态对象**
这个示例展示了如何修改类的酸洗行为。`TextReader` 类打开一个文本文件，并在每次调用其 `readline()` 方法时返回行号和行内容。

1.  如果文本阅读器实例被腌制，除文件对象成员之外的所有属性都将被保存。
2.  解除实例锁定后，将重新打开文件，并从最后一个位置继续读取。

## Python Pickle 模块示例

```py
import pickle

class TextReader:
    """Print and number lines in a text file."""

    def __init__(self, filename):
        self.filename = filename
        self.file = open(filename)
        self.lineno = 0

    def readline(self):
        self.lineno + 1
        line = self.file.readline()
        if not line:
            return None
        if line.endswith('\n'):
            line = line[:-1]
        return "%i: %s" % (self.lineno, line)

    def __getstate__(self):
        # Copy the object's state from self.__dict__ which contains
        # all our instance attributes. Always use the dict.copy()
        # method to avoid modifying the original state.
        state = self.__dict__.copy()
        # Remove the unpicklable entries.
        del state['file']
        return state

    def __setstate__(self, state):
        # Restore instance attributes (i.e., filename and lineno).
        self.__dict__.update(state)
        # Restore the previously opened file's state. To do so, we need to
        # reopen it and read from it until the line count is restored.
        file = open(self.filename)
        for _ in range(self.lineno):
            file.readline()
        # Finally, save the file.
        self.file = file

reader = TextReader("Geeksforgeeks.txt")
print(reader.readline())
print(reader.readline())
new_reader = pickle.loads(pickle.dumps(reader))
print(new_reader.readline())
```

**输出:**

```py
0: hi geeks!, this is line 1.
0: This is line 2.
0: hi geeks!, this is line 1.
```

本文由**阿迪提·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

这里是 `PickleViewer` 的一个编辑器:
[点击这里获取 Github Repo](https://github.com/Matix-Media/PickleViewer)
[点击这里获取 0.7.5 版本](https://github.com/Matix-Media/PickleViewer/raw/master/versions/0.7.5/PickleViewer075_setup.exe)的下载或者[点击这里获取最新版本](https://github.com/Matix-Media/PickleViewer/releases)
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。