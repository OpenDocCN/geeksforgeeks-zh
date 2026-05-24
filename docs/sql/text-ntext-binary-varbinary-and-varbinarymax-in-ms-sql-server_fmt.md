# MS SQL Server 中的 `text`、`ntext`、`binary`、`varbinary` 和 `varbinary(max)`

> 原文：[https://www.geeksforgeeks.org/text-ntext-binary-varbinary-and-varbinarymax-in-ms-sql-server/](https://www.geeksforgeeks.org/text-ntext-binary-varbinary-and-varbinarymax-in-ms-sql-server/)

字符（`char`）和可变字符（`varchar`）用于存储固定长度的单词。这些数据类型用于小规模创建数据库。假设我们有一个企业，它有各种各样的产品。数据库必须存储产品详细信息，包括其描述。我们有 `char` 和 `varchar`，但是它们能够存储文字段落吗？否。在这种情况下，使用 `text` 数据类型。

`text` 可以存储 1 到 4 千兆字节的数据。我们需要在 `char` 和 `varchar` 中指定长度，但是在 `text` 的情况下，我们不需要指定长度。然而，`text` 的运行速度比 `char` 和 `varchar` 慢。有 4 个子类别：

## `tinytext`
它是非 Unicode 字符串数据类型，最多可存储 255 个字符的数据。

## `text`
它是非 Unicode 字符串数据类型，存储大约 64KB 的数据。

## `mediumtext`
它最多存储 16MB 的数据。我们可以用 `mediumtext` 写描述长度的数据。

## `longtext`
我们可以使用这种非 Unicode 数据类型存储最多 4GB 的数据。使用这种数据类型，我们可以输入长达一篇文章的数据。

## `ntext`
无需指定长度即可存储数据的 Unicode 数据类型。存储大小是列中指定大小的两倍。`ntext` 没有子类别。

在少数情况下，我们可能需要在数据库中存储文件、图像。为了存储这种类型的数据，有一个名为 `binary` 的数据类型可以存储这种类型的数据。它有子类型，有助于根据存储大小存储相关数据。根据用户的要求，我们可以使用可变长度或固定长度。

## `binary`
`binary` 是存储图片、文件和其他媒体的固定长度数据类型。存储大小取决于指定的长度。它最多可以存储 8000 字节。

## `varbinary`
顾名思义，存储可变长度数据。存储取决于指定的字节数。

## `varbinary(max)`
它存储的最大大小可达 2GB。可变长度数据类型 `varbinary(max)` 可用于需要大容量的介质。

[MS SQL Server 中的 `varchar`、`varchar(max)` 和 `nvarchar`](https://www.geeksforgeeks.org/varchar-varcharmax-and-nvarchar-in-ms-sql-server/)