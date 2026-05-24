# SQL |子查询

> 原文:[https://www.geeksforgeeks.org/sql-subquery/](https://www.geeksforgeeks.org/sql-subquery/)

在 SQL 中，子查询可以简单地定义为另一个查询中的一个查询。换句话说，我们可以说子查询是嵌入在另一个 SQL 查询的 WHERE 子句中的查询。

子查询的重要规则:

*   您可以将子查询放在多个 SQL 子句中: [WHERE](https://www.geeksforgeeks.org/sql-where-clause/) 子句、 [HAVING](https://www.geeksforgeeks.org/having-vs-where-clause/) 子句、FROM 子句。
    子查询可以与 SELECT、UPDATE、INSERT、DELETE 语句以及表达式运算符一起使用。它可以是相等运算符或比较运算符，如=、>、=、< =和 Like 运算符。
*   子查询是另一个查询中的查询。外部查询称为**主查询**，内部查询称为**子查询**。
*   子查询通常首先执行，其输出用于完成主查询或外部查询的查询条件。
*   子查询必须用括号括起来。
*   子查询位于比较运算符的右侧。
*   [ORDER BY](https://www.geeksforgeeks.org/sql-order-by/) 命令**不能在子查询中使用**。 [GROUPBY](https://www.geeksforgeeks.org/sql-group-by/) 命令可用于执行与 ORDER BY 命令相同的功能。
*   对单行子查询使用单行运算符。对多行子查询使用多行运算符。

**语法:**
子查询没有任何通用语法。但是，子查询在 SELECT 语句中使用最频繁，如下所示:

```sql
SELECT column_name
FROM table_name
WHERE column_name *expression operator* 
    ( SELECT COLUMN_NAME  from TABLE_NAME   WHERE ... );

```

**样表**:

数据库

| 名字 | 滚动 _ 否 | 位置 | 电话号码 |
| 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | One hundred and one | 金奈 | Nine billion nine hundred and eighty-eight million seven hundred and seventy-five thousand five hundred and sixty-six |
| 统治 | One hundred and two | 哥印拜陀 | Eight billion eight hundred and seventy-seven million six hundred and sixty-five thousand five hundred and forty-four |
| Sasi | One hundred and three | 马杜赖 | Seven billion seven hundred and sixty-six million five hundred and fifty-three thousand three hundred and forty-four |
| 拉维河 | One hundred and four | 塞勒姆 | Eight billion nine hundred and eighty-nine million eight hundred and ninety-eight thousand nine hundred and eighty-nine |
| Sumathi | One hundred and five | Kanchipuram | Eight billion nine hundred and eighty-nine million eight hundred and fifty-six thousand eight hundred and sixty-eight |

学生

| 名字 | 滚动 _ 否 | 部分 |
| 拉维河 | One hundred and four | A |
| Sumathi | One hundred and five | B |
| 统治 | One hundred and two | A |

**样本查询**

：

*   To display NAME, LOCATION, PHONE_NUMBER of the students from DATABASE table whose section is A

    ```sql
    Select NAME, LOCATION, PHONE_NUMBER from DATABASE 
    WHERE ROLL_NO IN
    (SELECT ROLL_NO from STUDENT where SECTION=’A’); 

    ```

    **解释:**第一个子查询执行“从学生表中选择 ROLL_NO，其中 SECTION='A '”从 SECTION 为' A '的学生表中返回 ROLL_NO。然后外部查询执行它，并从数据库表中返回学生的姓名、位置、电话号码，该学生的 ROLL_NO 是从内部子查询中返回的。
    产量:

    | 名字 | 滚动 _ 否 | 位置 | 电话号码 |
    | 拉维河 | One hundred and four | 塞勒姆 | Eight billion nine hundred and eighty-nine million eight hundred and ninety-eight thousand nine hundred and eighty-nine |
    | 统治 | One hundred and two | 哥印拜陀 | Eight billion eight hundred and seventy-seven million six hundred and sixty-five thousand five hundred and forty-four |

*   Insert Query Example:

    表 1:学生 1

    | 名字 | 滚动 _ 否 | 位置 | 电话号码 |

    随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写)One hundred and onechennaiNine billion nine hundred and eighty-eight million seven hundred and seventy-three thousand three hundred and forty-four拉朱One hundred and two哥印拜陀Nine billion ninety million nine hundred and nine thousand and ninety拉维河One hundred and three塞伦8989898989

    表 2:学生 2

    | 名字 | 滚动 _ 否 | 位置 | 电话号码 |

    统治One hundred and elevenchennaiEight billion seven hundred and eighty-seven million eight hundred and seventy-eight thousand seven hundred and eighty-seven日本短剑One hundred and twelve孟买Six billion five hundred and sixty-five million six hundred and fifty-six thousand five hundred and sixty-five斯里One hundred and thirteen哥印拜陀7878787878

    要将 Student2 插入 Student1 表:

    ```sql
    INSERT INTO Student1  SELECT * FROM Student2;

    ```

    输出:

    | 名字 | 滚动 _ 否 | 位置 | 电话号码 |

    随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写)One hundred and onechennaiNine billion nine hundred and eighty-eight million seven hundred and seventy-three thousand three hundred and forty-four拉朱One hundred and two哥印拜陀Nine billion ninety million nine hundred and nine thousand and ninety拉维河One hundred and three塞伦Eight billion nine hundred and eighty-nine million eight hundred and ninety-eight thousand nine hundred and eighty-nine统治One hundred and elevenchennaiEight billion seven hundred and eighty-seven million eight hundred and seventy-eight thousand seven hundred and eighty-seven日本短剑One hundred and twelve孟买Six billion five hundred and sixty-five million six hundred and fifty-six thousand five hundred and sixty-five斯里One hundred and thirteen哥印拜陀7878787878
*   删除学生 2 表格中的学生，该表格的序号与学生 1 表格中的序号相同，并且位置与钦奈相同

    ```sql
    DELETE FROM Student2 
    WHERE ROLL_NO IN ( SELECT ROLL_NO 
                       FROM Student1 
                       WHERE LOCATION = ’chennai’);

    ```

    输出:

    ```sql
    1 row delete successfully.

    ```

    **显示学生 2 表:**

    T21

    | 名称 | ROLL_NO | 地点 | PHONE _ NUMBER |

    T25】赛112T29】孟买6565656565T34斯里T37】113【T33 学生对学生 2 表中的极客，其位置与学生 1 表中的拉朱、拉维相同

    ```sql
    UPDATE Student2 
    SET NAME=’geeks’ 
    WHERE LOCATION IN ( SELECT LOCATION 
                        FROM Student1 
                        WHERE NAME IN (‘Raju’,’Ravi’));

    ```

    输出:

    ```sql
    1 row updated successfully.

    ```

    **显示学生 2 表:**

    T59

    | NAME | ROLL _ NO | LOCATION | PHONE _ NUMBER |

    T62Sai112孟买65656565T72】

本文由**冉亚尼拉维**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。