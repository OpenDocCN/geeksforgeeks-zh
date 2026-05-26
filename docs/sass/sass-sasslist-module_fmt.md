# Sass 列表模块

> 原文: [https://www.geeksforgeeks.org/sass-sasslist-module/](https://www.geeksforgeeks.org/sass-sasslist-module/)

Sass 提供了许多内置模块，包含各种有用的功能和一些混合，使其易于使用。所有内置模块都以 `sass:` 开头，表明它们不同于其他模块，是 Sass 本身的一部分。其中一个内置模块是 `sass:list` 模块，可以访问和修改列表中的值。

**注意:** 在 Sass 中，每个映射都算作一个列表，其中包含每个键/值对的两个元素。例如，`(1: 2, 3: 4)` 计为 `(1 2, 3 4)`。所以下面讨论的所有函数都适用于地图和列表。此模块允许您访问和修改列表。

## 列表模块方法

在 `list` 模块中有以下方法:

### `list.append()`

此函数返回列表的副本，并在末尾添加给定的值。

**语法:**

```scss
list.append($list, $val, $separator: auto)
append($list, $val, $separator: auto)
```

如果分隔符是 `comma`，那么返回的列表将以逗号分隔，空格分隔也是如此。如果分隔符是 `auto` (默认分隔符)，返回的列表将使用与列表相同的分隔符 (如果列表没有分隔符，则为空格)。分隔符中不允许有其他值。与 `list.join()` 不同，如果值是一个列表，那么它将嵌套在返回的列表中，而不是将每个元素添加到返回的列表中。

**示例:**

```scss
@debug list.append(10px 20px, 30px);
@debug list.append((geeks, for), geeks);
@debug list.append(10px 20px, 30px 40px);
@debug list.append(10px, 20px, $separator: comma);
@debug list.append((geeks, for), geeks, $separator: space);
```

**输出:**

```scss
10px 20px 30px
geeks, for, geeks
10px 20px (30px 40px)
10px, 20px
geeks for geeks
```

### `list.index()`

此函数返回值在列表中的索引。

**语法:**

```scss
list.index($list, $value)
index($list, $value)
```

如果该值没有出现在列表中，该函数返回 `null`。如果该值在列表中出现多次，函数将返回该值第一次出现的索引。

**示例:**

```scss
@debug list.index(geeks for geeks, geeks);
@debug list.index(geeks for geeks, for);
@debug list.index(geeks for geeks, slash_it);
```

**输出:**

```scss
null
```

### `list.join()`

此函数返回一个新列表，其中包含 `list1` 的元素，后跟 `list2` 的元素。

**语法:**

```scss
list.join($list1, $list2,
    $separator: auto, $bracketed: auto)
join($list1, $list2,
    $separator: auto, $bracketed: auto)
```

如果分隔符是 `comma`，那么返回的列表将以逗号分隔，以空格分隔也是如此。在 `auto` (默认分隔符) 的情况下，如果有分隔符，返回的列表将使用与 `list1` 相同的分隔符；如果有分隔符，返回的列表将使用 `list2`，否则将使用空格作为分隔符。分隔符中不允许有其他值。如果方括号设置为 true，则返回的列表由方括号组成。否则，返回的列表没有任何括号。如果是 `auto` (默认)，则返回的列表会被括起来。不允许其他值。

**示例:**

```scss
@debug list.join(10px 20px, 30px 40px);
@debug list.join((geeks, for), (geeks, gfg));
@debug list.join(10px, 20px);
@debug list.join(10px, 20px, $separator: comma);
@debug list.join((geeks, for),
    (geeks, gfg), $separator: space);
@debug list.join([10px], 20px);
@debug list.join(10px, 20px, $bracketed: true);
```

**输出:**

```scss
10px 20px 30px 40px
geeks, for, geeks, gfg
10px 20px
10px, 20px
geeks for geeks gfg
[10px 20px]
[10px 20px]
```

### `list.length()`

此函数返回列表的长度。

**语法:**

```scss
list.length($list)
length($list)
```

这个函数也可以用来返回地图中的对的数量。

**示例:**

```scss
@debug list.length(geeks);
@debug list.length(geeks for geeks);
@debug list.length((gfg: geeksforgeeks,
            slash_it: Shivam));
```

**输出:**

```scss

```

### `list.nth()`

此函数返回列表中索引为 `n` 的元素。

**语法:**

```scss
list.nth($list, $n)
nth($list, $n)
```

如果 `n` 为非正整数，此函数从列表末尾开始计数。如果索引 `n` 中没有元素，它会抛出一个错误。

**示例:**

```scss
@debug list.nth(geeks for geeks, 2);
@debug list.nth([geeks for geeks], 3);
```

**输出:**

```scss
for
geeks
```