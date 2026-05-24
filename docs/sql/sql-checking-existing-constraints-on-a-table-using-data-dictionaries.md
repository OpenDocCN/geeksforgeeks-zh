# SQL |使用数据字典检查表的现有约束

> 原文:[https://www . geesforgeks . org/SQL-检查-现有-表约束-使用数据-字典/](https://www.geeksforgeeks.org/sql-checking-existing-constraints-on-a-table-using-data-dictionaries/)

**先决条件**:[SQL-约束](https://www.geeksforgeeks.org/sql-constraints/)

在 SQL Server 中，**数据字典**是一组用于存储数据库定义信息的数据库表。可以使用这些数据字典来检查已经存在的表上的约束，并对其进行更改(如果可能的话)。

*   **USER_CONSTRAINTS Data Dictionary:** This data dictionary contains information about each constraint used in a database along with constraint specific information.

    ```sql
    DESC USER_CONSTRAINTS;

    Name              Null     Type         
    ----------------- -------- ------------ 
    OWNER                      VARCHAR2(30) 
    CONSTRAINT_NAME   NOT NULL VARCHAR2(30) 
    CONSTRAINT_TYPE            VARCHAR2(1)  
    TABLE_NAME        NOT NULL VARCHAR2(30) 
    SEARCH_CONDITION           LONG         
    R_OWNER                    VARCHAR2(30) 
    R_CONSTRAINT_NAME          VARCHAR2(30) 
    DELETE_RULE                VARCHAR2(9)  
    STATUS                     VARCHAR2(8)  
    DEFERRABLE                 VARCHAR2(14) 
    DEFERRED                   VARCHAR2(9)  
    VALIDATED                  VARCHAR2(13) 
    GENERATED                  VARCHAR2(14) 
    BAD                        VARCHAR2(3)  
    RELY                       VARCHAR2(4)  
    LAST_CHANGE                DATE         
    INDEX_OWNER                VARCHAR2(30) 
    INDEX_NAME                 VARCHAR2(30) 
    INVALID                    VARCHAR2(7)  
    VIEW_RELATED               VARCHAR2(14) 

    ```

    约束类型有:

    ```sql
    C - Check constraint on a table  
    P - Primary key  
    U - Unique key  
    R - Referential integrity  
    V - With check option, on a view  
    O - With read only, on a view  
    H - Hash expression  
    F - Constraint that involves a REF column  
    S - Supplemental logging

    ```

    现在考虑下面的源表“SDF”:

    ```sql
    SUPPNO  SNAME   STATUS  CITY
    21    JONYY    25    NY
    22    MIKKY    11    LA
    23    JIM    29    LV
    24    BNFERYY    47    HW
    25    TIM    41    HS

    ```

    用于检查此表约束的查询:

    ```sql
    SELECT CONSTRAINT_NAME, SEARCH_CONDITION AS CONSTRAINT_TYPE 
    FROM USER_CONSTRAINTS 
    WHERE TABLE_NAME='SDF';

    ```

    **输出**:

    | 约束名 | 约束类型 |
    | --- | --- |
    | XYZ | 状态< 50 |
    | 字母表 | (空) |

*   **用户 _ CONS _ 列数据字典：**

```sql
DESC USER_CONS_COLUMNS;

Name            Null     Type           
--------------- -------- -------------- 
OWNER           NOT NULL VARCHAR2(30)   
CONSTRAINT_NAME NOT NULL VARCHAR2(30)   
TABLE_NAME      NOT NULL VARCHAR2(30)   
COLUMN_NAME              VARCHAR2(4000) 
POSITION                 NUMBER     

```

查询以检查带有约束的 SDF 表的列:

```sql
SELECT * FROM USER_CONS_COLUMNS WHERE TABLE_NAME='SDF';

```

**输出**:

| 物主 | 约束名 | 表名 | 列名 | 位置 |
| --- | --- | --- | --- | --- |
| 系统 | XYZ | 自卫队 | 状态 | (空) |
| 系统 | 字母表 | 自卫队 | 状态 | one |

*   **Using Cartesian Product to get Complete information on constraints:**

    ```sql
    SELECT A.CONSTRAINT_NAME, A.CONSTRAINT_TYPE, B.COLUMN_NAME, B.TABLE_NAME
    FROM 
    USER_CONSTRAINTS A,
    USER_CONS_COLUMNS B
    WHERE A.CONSTRAINT_NAME=B.CONSTRAINT_NAME
    AND A.TABLE_NAME='SDF';

    ```

    **输出**:

    | 约束名 | 约束类型 | 列名 | 表名 |
    | --- | --- | --- | --- |
    | XYZ | C | 状态 | 自卫队 |
    | 字母表 | P | 苏比诺 | 自卫队 |