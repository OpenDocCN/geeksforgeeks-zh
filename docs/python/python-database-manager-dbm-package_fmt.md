# Python–数据库管理器(dbm)包

> 原文: [https://www.geeksforgeeks.org/python-database-manager-dbm-package/](https://www.geeksforgeeks.org/python-database-manager-dbm-package/)

在本文中，我们将了解 `dbm`，一个内置 python 库的包。python 中的 `dbm` 包提供了一个简单的字典式接口，类似于 Unix 操作系统中通常使用的 DBM (DataBase Manager)形式。`dbm` 像字典一样以简单的键值对形式存储数据，这使得从数据库中插入、编辑和检索数据变得更加容易。它通过在固定大小的块中使用单个主键(“键”)来存储数据。

`dbm` 包中有三种类型的子模块:

1.  `dbm.gnu`: GNU 对 dbm 的重新诠释
2.  `dbm.ndbm`: 基于 ndbm 的接口
3.  `dbm.dumb`: 便携式 dbm 实现

## dbm 包中可用的主要功能

### `dbm.open()`

该函数用于打开一个 dbm 数据库或创建一个新的数据库(如果不存在的话)。

> **语法:** `dbm.open(file, flag='r', mode=0o666)`
>
> **参数:** 该函数采用以下参数:
>
> *   `file`: 文件的名称。
> *   `flag`: 权限模式。可以是 `'r'`、`'w'`、`'c'` 或 `'n'`。
>     *   `'r'`: 以只读权限打开现有数据库。
>     *   `'w'`: 以读写权限打开已有数据库。
>     *   `'c'`: 打开数据库进行读写，如果不存在也新建一个。
>     *   `'n'`: 始终创建一个具有读写权限的新数据库。
> *   `mode`: 参数的 Unix 模式，八进制默认设置为 `0o666`，仅在创建新数据库时使用。
>
> **返回:** 数据库文件对应的对象地址。

### `dbm.whichdb()`

该函数试图猜测可用的几个简单数据库模块- `dbm.gnu`、`dbm.ndbm` 或 `dbm.dumb`- 中的哪一个应该用于打开给定的文件。

> **语法:** `dbm.whichdb(filename)`
>
> **参数:** `filename` - 文件名。
>
> **返回:** 函数返回以下值之一:
>
> *   `None`: 如果数据库不存在或无法打开。
> *   `''`: 一个空字符串，如果文件存在但文件格式不能被其他人猜到。
> *   所需的模块名称: 如果成功检测到类型，则返回字符串名称之一，`"dbm.gnu"`、`"dbm.ndbm"` 或 `"dbm.dumb"`。

## dbm 对象的内置方法

> *   `items()`: This method returns the items contained in the caller object database in the form of key-value pairs. (db is the caller object database).
> *   `clear()`: Clear all values in the database.
> *   `get(key)`: Returns the value corresponding to the key given in the parameter.
> *   `keys()`, `iterkeys()`: Returns an iterative list containing dictionary keys.
> *   `pop(key)`: Delete/eject the key and value pair corresponding to the given key in the parameter.
> *   `setdefault()`: Set the default primary key given in the parameter.
> *   `sync()`: Helps synchronize data files with directories on disk.
> *   `update()`: Update the existing key value. Just like a dictionary object.
> *   `values()`: Traverse all the values existing in the database.
> *   `close()`: It does not accept any parameters or return anything. Just shut down the caller object database. (db in this example)

以下是上述所有讨论方法/功能的实现:

## 代码

```py
# importing the dbm package
import dbm

# using the open function
# to create a new database named
# 'mydb' in 'n' mode, object
# returned in db variable.
db = dbm.open('mydb','n')

# inserting the new key and
# values in the database.
db['name'] = 'GeeksforGeeks'
db['phone'] = '8888'
db['Short name'] = 'GfG'
db['Date'] = '01/01/2000'

# getting and printing
# the value through get method.
print(db.get('name'))
print()

# printing the values of
# database through values()
# method (iterator).
for value in db.values():
    print(value)
print()

# printing the values through
# key iterator.
for key in db.keys():
    print(db.get(key))
print()

# poping out the key, value
# pair corresponding to
# 'phone' key.
db.pop('phone')

# printing the key, value
# pairs present in database.
for key, value in db.items():
    print(key, value)

# clearing all the key values
# in database.
db.clear()

# Below loop will print nothing
# as database is cleared above.
for key, value in db.items():
    print(key, value)

# closing the database.
db.close()

# This code is contributed by Amit Mangal.
```

## 输出

```py
b'GeeksforGeeks'

b'GeeksforGeeks'
b'8888'
b'GfG'
b'01/01/2000'

b'GeeksforGeeks'
b'8888'
b'GfG'
b'01/01/2000'

b'name' b'GeeksforGeeks'
b'Short name' b'GfG'
b'Date' b'01/01/2000'
```