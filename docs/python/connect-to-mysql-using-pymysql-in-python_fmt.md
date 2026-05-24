# 使用 Python 中的 PyMySQL 连接到 MySQL

> 原文: [https://www.geeksforgeeks.org/connect-to-mysql-using-pymysql-in-python/](https://www.geeksforgeeks.org/connect-to-mysql-using-pymysql-in-python/)

在本文中，我们将讨论如何使用 Python 远程连接 `MySQL` 数据库或本地连接。在下面的过程中，我们将使用 Python 的 `PyMySQL` 模块来连接我们的数据库。

## 什么是 `PyMySQL`？

这个包包含一个基于 PEP 249 的纯 Python MySQL 客户端库。

**要求：**

*   `MySQL Server` – 以下之一:
    *   `MySQL >= 5.5`
    *   `Maria database >= 5.5`

**安装：**

这个模块没有内置 Python。你必须从外部安装它。要安装此软件，请在终端中键入以下命令。

```py
pip install PyMySQL
```

## 连接到 MySQL

获取该类实例的正确方法是调用 `connect()` 方法。此方法建立与 MySQL 数据库的连接，并接受几个参数:

> **参数:**
> *   `Host` – 数据库服务器所在的主机。
> *   `User` – 登录使用的用户名。
> *   `Password` - 要使用的密码。
> *   `Database` – 要使用的数据库，如果不指定则不使用特定数据库。
> *   `Port` – 使用的 MySQL 端口，通常默认值即可。(默认: `3306`)

**示例 1:** 让我们连接到 MySQL 服务器。

```py
import pymysql

def mysqlconnect():
    # To connect MySQL database
    conn = pymysql.connect(
        host='localhost',
        user='root', 
        password = "pass",
        db='College',
        )

    cur = conn.cursor()
    cur.execute("select @@version")
    output = cur.fetchall()
    print(output)

    # To close the connection
    conn.close()

# Driver Code
if __name__ == "__main__" :
    mysqlconnect()
```