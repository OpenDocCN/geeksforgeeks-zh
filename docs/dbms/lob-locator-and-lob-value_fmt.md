# LOB 定位器和 LOB 值

> 原文:[https://www.geeksforgeeks.org/lob-locator-and-lob-value/](https://www.geeksforgeeks.org/lob-locator-and-lob-value/)

有两种方法可用于访问和修改业务线值:

*   使用业务线数据接口
*   使用业务线定位器访问/修改业务线值

## 使用 LOBs 的数据接口

您可以使用 LOB 的数据接口在 C 应用程序中对 `BLOB` 和 `CLOB` 列执行绑定和定义操作。它使您能够在不使用业务线定位器的情况下插入或选择业务线列中的数据如下:

*   将字符数据插入 `CLOB` 或将原始数据插入 `BLOB`，这需要借助与业务线列关联的绑定变量。
*   `Define` 操作用于在应用程序中定义一个输出缓冲区，以存储从 `BLOB` 选择的 `RAW` 数据或从 `CLOB` 选择的字符数据。

## 使用业务线定位器访问/修改业务线值

存储在数据库中的业务线实例的值可以通过业务线定位器(对业务线值位置的引用)来访问。数据库表只在 `CLOB`、`BLOB`、`NCLOB` 和 `BFILE` 列中存储定位器。以下是关于业务线定位器和值的要点:

*   要操作或访问 `LOB` 值，您可以将 `LOB` 定位器传递给各种 `LOB` 应用程序编程接口。
*   该业务线定位器可以轻松地分配或重新分配给任何相同类型的业务线实例。
*   `LOB` 的临时或持久特性独立于定位器。或者说临时持久性仅适用于业务线实例。

## LOB 定位器和 BFILE 定位器

`LOB` 类型 `CLOB`、`NCLOB` 和 `BLOB` 的定位器语义与 `BFILE` 类型的定位器语义之间几乎没有区别:

*   对于 `LOB` 类型 `CLOB`、`NCLOB` 和 `BLOB`，`LOB` 列存储一个指向 `LOB` 值的定位器。每个业务线实例都有其自身唯一的业务线值副本和唯一的业务线定位器。
*   对于已初始化的 `BFILE` 列，该行存储指向外部操作系统文件的定位器，该文件保存着 `BFILE` 的值。给定行中的每个 `BFILE` 实例都有其自身唯一的定位器；然而，两个不同的行可以包含一个指向同一个操作系统文件的 `BFILE` 定位器。

无论业务线的值存储在哪里，定位器都会存储在任何已初始化的业务线列的表行中。每当使用没有识别前缀术语的术语“定位器”时，它指的是 `LOB` 定位器和 `BFILE` 定位器。此外，每当您从表中选择一个业务线时，返回的业务线总是一个临时业务线。有关使用临时 `lob` 定位器的更多信息，请参见“从 SQL 函数返回的 `lob`”。

## 表 print_media

Oracle 数据库示例模式 `PM` 的表`print_media`用作许多示例，定义为:

```sql
CREATE TABLE print_media
    ( product_id NUMBER(6), 
      ad_id NUMBER(6), 
      ad_composite BLOB, 
      ad_sourcetext CLOB, 
      ad_finaltext CLOB, 
      ad_fltextn NCLOB, 
      ad_textdocs_ntab textdoc_tab, 
      ad_photo BLOB, 
      ad_graphic BFILE, 
      ad_header adheader_typ
    ) 
NESTED TABLE ad_textdocs_ntab STORE AS textdocs_nestedtab;
```