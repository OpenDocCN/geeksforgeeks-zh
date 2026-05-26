# 如何将熊猫数据框插入到现有的 PostgreSQL 表中？

> 原文：[https://www.geeksforgeeks.org/how-to-insert-a-pandas-dataframe-to-an-existing-postgresql-table/](https://www.geeksforgeeks.org/how-to-insert-a-pandas-dataframe-to-an-existing-postgresql-table/)

在本文中，我们将看到如何向现有的 PostgreSQL 表中插入 `pandas` `DataFrame`。

## 需要的模块

*   `pandas`：`Pandas` `DataFrame` 是一个二维可变大小的、潜在异构的表格数据结构，带有标记轴（行和列）。数据框是一种二维数据结构，即数据以表格形式排列成行和列。熊猫数据框架由三个主要部分组成，即数据、行和列。
*   `psycopg2`：`PostgreSQL` 是一个功能强大的开源对象关系数据库系统。`PostgreSQL` 运行在所有主要的操作系统上。`PostgreSQL` 遵循数据库系统的 `ACID` 属性，支持触发器、可更新视图和物化视图、外键。
*   `sqlalchemy`：`SQLAlchemy` 是 `Python` `SQL` 工具包和对象关系映射器，为应用程序开发人员提供了 `SQL` 的全部功能和灵活性。

我们通过导入包并创建格式为 `postgres://user:password@host/database` 的连接字符串来启动代码。

`create_engine()` 函数以连接字符串为参数，形成与 `PostgreSQL` 数据库的连接，连接后我们创建一个字典，并使用 `pandas` 的 `DataFrame()` 方法进一步将其转换为数据帧。

`to_sql()` 方法用于将熊猫数据框插入 `Postgresql` 表中。最后，我们使用 `execute()` 方法执行命令来执行我们的 `SQL` 命令，并使用 `fetchall()` 方法来获取记录。

> `df.to_sql('data', con=conn, if_exists='replace', index=False)`
>
> 参数有：
>
> *   表的名称
> *   关系
> *   `if_exists`：如果表已经存在，我们要应用的函数。例如：“append”帮助我们添加数据，而不是替换数据。
> *   `index`：真或假

## 例 1

使用 `sqlalchemy` 将 `pandas` `DataFrame` 插入现有的 `PostgreSQL` 表。在以下示例中，用于在 `PostgreSQL` 数据库中创建表的 `create table` 命令是：

> `create table data(name varchar, age varchar);`

### 代码

```py
import psycopg2
import pandas as pd
from sqlalchemy import create_engine

conn_string = 'postgres://user:password@host/data1'

db = create_engine(conn_string)
conn = db.connect()

# our dataframe
data = {'Name': ['Tom', 'dick', 'harry'],
        'Age': [22, 21, 24]}

# Create DataFrame
df = pd.DataFrame(data)
df.to_sql('data', con=conn, if_exists='replace',
          index=False)
conn = psycopg2.connect(conn_string
                        )
conn.autocommit = True
cursor = conn.cursor()

sql1 = '''select * from data;'''
cursor.execute(sql1)
for i in cursor.fetchall():
    print(i)

# conn.commit()
conn.close()
```

### 输出

```py
('Tom', 22)
('dick', 21)
('harry', 24)
```

### PostgreSQL 中的输出

![](img/c96215af863b50fc67e6272aaa2e1ab1.png)

PostgreSQL 中的输出表

## 例 2

在不使用 `sqlalchemy` 的情况下，将 `pandas` `DataFrame` 插入现有的 `PostgreSQL` 表。像往常一样，我们使用 `connect()` 命令与 `PostgreSQL` 建立连接，并执行 `execute_values()` 方法，在那里执行“插入” `SQL` 命令。包含了一个 `try-except` 子句，以确保错误被捕获（如果有的话）。

要查看或下载下面程序中使用的 `CSV` 文件：点击这里的。

在以下示例中，用于在 `PostgreSQL` 数据库中创建表的 `create table` 命令是：

> `create table fossil_fuels_c02(year int, country varchar, total int, solid_fuel int, liquid_fuel int, gas_fuel int, cement int, gas_flaring int, per_capita int, bunker_fuels int);`

### 代码

```py
import psycopg2
import numpy as np
import psycopg2.extras as extras
import pandas as pd

def execute_values(conn, df, table):

    tuples = [tuple(x) for x in df.to_numpy()]

    cols = ','.join(list(df.columns))
    # SQL query to execute
    query = "INSERT INTO %s(%s) VALUES %%s" % (table, cols)
    cursor = conn.cursor()
    try:
        extras.execute_values(cursor, query, tuples)
        conn.commit()
    except (Exception, psycopg2.DatabaseError) as error:
        print("Error: %s" % error)
        conn.rollback()
        cursor.close()
        return 1
    print("the dataframe is inserted")
    cursor.close()

conn = psycopg2.connect(
    database="ENVIRONMENT_DATABASE", user='postgres', password='pass', host='127.0.0.1', port='5432'
)

df = pd.read_csv('fossilfuels.csv')

execute_values(conn, df, 'fossil_fuels_c02')
```

### 输出

```py
the dataframe is inserted
```

![](img/9d3d60f93dc372a4f703fdfb9c6f65d1.png)

插入数据帧后