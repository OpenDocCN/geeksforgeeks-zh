# CQL 的数据库角色（卡珊德拉查询语言）

> 原文：[https://www.geeksforgeeks.org/database-roles-in-cql-cassandra-query-language/](https://www.geeksforgeeks.org/database-roles-in-cql-cassandra-query-language/)

在本文中，我们将讨论卡珊德拉查询语言中的数据库角色。为不同类型的用户创建不同的角色以提供具有特定需求的访问是非常重要的。它用于为数据库用户或用户组提供安全性。

角色名称可以简单地定义如下。

```
role_name ::= identifier | string
```

## `CREATE ROLE`

在 CQL 中，我们可以使用 `CREATE` 命令语句来创建角色。`CREATE` 命令有助于为用户或用户组创建角色。

**语法：**

```
create_role_statement ::=  CREATE ROLE [ IF NOT EXISTS ] role_name
                               [ WITH role_options ]
role_options          ::=  role_option ( AND role_option )*
role_option           ::=  PASSWORD '=' string
                          | LOGIN '=' boolean
                          | SUPERUSER '=' boolean
                          | OPTIONS '=' map_literal
                          | ACCESS TO DATACENTERS set_literal
                          | ACCESS TO ALL DATACENTERS 
```

[来源](http://cassandra.apache.org/doc/latest/cql/security.html#database-roles)

**简单语法：**

```
CREATE ROLE new_role_name; 
```

**例如：**

创建简单用户和超级用户角色，然后使用以下 CQL 查询。

```
CREATE ROLE Ashish WITH PASSWORD = 'pass_a' 
                         AND LOGIN = true;
CREATE ROLE Rana WITH PASSWORD = 'pass_r' 
                  AND LOGIN = true 
                  AND SUPERUSER = true;
```

要为具有更多限制的用户创建数据库角色，以便如果用户只能访问特定的数据中心，那么要创建这种类型的角色，请使用以下 CQL 查询。

```
CREATE ROLE user1 WITH OPTIONS = { 'option1' : 'option1_value', 
                                   'option2' : 98 };
CREATE ROLE Ashish WITH PASSWORD = 'pass_a' 
                    AND LOGIN = true 
                    AND ACCESS TO DATACENTERS {'DC1', 'DC4'};
CREATE ROLE Rana WITH PASSWORD = 'pass_r' 
                  AND LOGIN = true 
                  AND ACCESS TO ALL DATACENTERS;
```

如果我们想有条件地创建角色，那么我们可以使用下面的 CQL 查询。

```
CREATE ROLE IF NOT EXISTS role_name; 
```

## `ALTER ROLE`

如果我们想要更改已创建的现有角色，那么我们可以使用 `ALTER ROLE` 语句来修改角色。

**语法：**

```
alter_role_statement ::=  ALTER ROLE role_name 
                          WITH role_options 
```

**例如：**

在改变角色之前：

```
CREATE ROLE Rana WITH PASSWORD = 'pass_r' 
                       AND LOGIN = true 
                       AND SUPERUSER = true;
```

改变角色后：

```
ALTER ROLE Rana WITH PASSWORD = 'pass_r' 
                      AND SUPERUSER = false;
```

## `DROP ROLE`

如果用户想要删除现有角色，那么我们可以使用以下 CQL 查询来删除角色。

**语法：**

```
drop_role_statement ::=  DROP ROLE [ IF EXISTS ] role_name
```

**例如：**

```
DROP ROLE Ashish;
```

## 授予角色

用于将角色授予其他用户。

**语法：**

```
grant_role_statement ::=  GRANT role_name 
                                  TO role_name
```

**例如：**

```
GRANT user1 TO Ashish;
```

此语句将 `user1` 角色授予 `Ashish`。授予 `user1` 的任何权限也由 `Ashish` 获得。

## 撤销角色

如果用户想要撤销数据库角色，那么我们可以使用 `REVOKE ROLE` 语句。

**语法：**

```
revoke_role_statement ::=  REVOKE role_name 
                                 FROM role_name
```

**例如：**

```
REVOKE user1 FROM Ashish;
```

上面的 CQL 查询语句取消了 `Ashish` 的 `user1` 角色。`Ashish` 通过 `user1` 角色获得的任何权限也会被撤销。

## 列出角色

如果用户想要列出所有的角色，那么我们可以使用下面的 CQL 查询来列出所有的角色。

**语法：**

```
list_roles_statement ::=  LIST ROLES [ OF role_name ] 
                                          [ NORECURSIVE ]
```

**例如：**

```
LIST ROLES;
```

这个 CQL 查询语句返回系统中所有已知的角色，这些角色需要数据库角色资源的 `description` 权限。