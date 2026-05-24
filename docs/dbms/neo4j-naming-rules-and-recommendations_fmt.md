# Neo4j 命名规则和建议

> 原文: [https://www.geeksforgeeks.org/neo4j-naming-rules-and-recommendations/](https://www.geeksforgeeks.org/neo4j-naming-rules-and-recommendations/)

几乎没有严格的命名规则，但节点标签、关系类型、属性名称和变量的命名必须遵循一些基本规则，除非出现错误。

## 命名规则

*   为节点标签、关系类型、属性名称和变量命名时，应以字母开头。这也适用于非英文字符。如果需要使用数字字符来命名上述任何内容，可以使用反引号（`）来转义非字母字符，例如 `` `n` ``。
*   名称可以包含数字，但不能放在首位，例如 `1geeks` 是不允许的。你可以将其命名为 `geek1` 或 `geek_1`。但是，如果必须在开头添加数字，也可以使用反引号来转义，就像 `` `1geek` `` 一样，反引号会跳过 `1`，而其他字符则按原样处理。
*   在 Neo4j 中的命名不能包含任何特殊的命名符号。但是，允许使用下划线。如果需要特殊符号，请使用反引号进行转义。
*   名称的长度可以是 65535（2^16-1）或 65534，这基本上取决于 Neo4j 的版本。
*   Neo4j 中的命名是区分大小写的，例如 `:Geeks`、`:geeks` 和 `:GEEKS` 是三个不同的标签，而 `g` 和 `G` 是不同的变量。
*   空白字符是可接受的，所有前导和尾随的空白字符都会被自动删除。例如 `match (a) return a` 等价于 `match (a) return a`。如果名称中需要空格，请使用反引号进行转义，例如 `` `My variable has a space` ``。

## 范围和命名空间规则

*   所有节点标签、关系类型和属性名称都可以重用名称。以下查询是有效的，其中标签、类型和属性名称都被重用了：

    ```cypher
    CREATE (a:a {a: 'a'})-[r:a]->(b:a {a: 'a'}).
    ```

*   节点和关系的变量在同一个查询范围内不能有重复的名称。以下查询是无效的，因为节点和关系都使用了名称 `a`：

    ```cypher
    CREATE (a)-[a]->(b)
    ```

## 推荐用于命名节点标签、关系类型、属性名称和变量

*   **节点标签：** 尝试使用驼峰命名法（Camel case），以大写字母开头，如下例所示。

    ```cypher
    :GeeksforGeeks rather than :geeksforgeeks
    ```

*   **关系类型：** 尝试使用大写字母，并使用下划线分隔单词。

    ```cypher
    :Geeks_for_Geeks rather than :geeksForGeeks
    ```

***参考:*** [https://neo4j.com/docs/cypher-manual/current/syntax/naming/](https://neo4j.com/docs/cypher-manual/current/syntax/naming/)