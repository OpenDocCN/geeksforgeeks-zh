# Sass: 地图模块

> 原文: [https://www.geeksforgeeks.org/sass-sassmap-module/](https://www.geeksforgeeks.org/sass-sassmap-module/)

`sass:map` 模块提供了一些函数，这些函数可以查找与地图的键相关联的值。下面列出了一些主要功能:

## `map.get()`

此函数返回地图中与给定键相关联的值。如果没有关联值，则返回 `null`。

### 语法

```scss
map.get($map, $key)
map-get($map, $key)
```

### 示例

```scss
$gfg: ("geeks": 5, "for": 3, "geeksforgeeks": 13);

@debug map.get($gfg, "geeks");
@debug map.get($gfg, "GFG");
```

### 输出

```scss
5
null
```

## `map.has-key()`

此函数返回任何值是否与地图中的给定键相关联。它返回 `true` 或 `false`。

### 语法

```scss
map.has-key($map, $key)
map-has-key($map, $key)
```

### 示例

```scss
$gfg: ("geeks": 5, "for": 3, "geeksforgeeks": 13);

@debug map.has-key($gfg, "geeks");
@debug map.has-key($gfg, "GFG");
```

### 输出

```scss
true
false
```

## `map.keys()`

此函数返回地图中所有键的逗号分隔列表。

### 语法

```scss
map.keys($map)
map-keys($map)
```

### 示例

```scss
$gfg: ("geeks": 5, "for": 3, "geeksforgeeks": 13);

@debug map.keys($gfg);
```

### 输出

```scss
"geeks", "for", "geeksforgeeks"
```

## `map.merge()`

此函数返回一个新地图，其中包含两个给定地图的所有键和值。该函数也可用于通过将单个键/值对作为第二个地图传递，来向一个地图添加新值或覆盖其中的值。如果两个地图具有相同的键，则第二个地图的值优先。返回地图中同时出现在第一个地图中的所有键保持其原有顺序。来自第二个地图的新键出现在地图的末尾。

### 语法

```scss
map.merge($map1, $map2)
map-merge($map1, $map2)
```

### 示例

```scss
$gfg: ("geeks": 5, "for": 3);
$slash: ("geeksforgeeks": 13);

@debug map.merge($gfg, $slash);
@debug map.merge($gfg, ("geeksforgeeks": 20));
@debug map.merge($gfg, ("geeks": 20));
```

### 输出

```scss
("geeks": 5, "for": 3, "geeksforgeeks": 13)
("geeks": 5, "for": 3, "geeksforgeeks": 20)
("geeks": 20, "for": 3)
```

## `map.remove()`

此函数返回给定地图的副本，但不包含在函数中调用的键及其关联值。如果地图中不存在该键，则忽略该键。

### 语法

```scss
map.remove($map, $keys...)
map-remove($map, $keys...)
```

### 示例

```scss
$gfg: ("geeks": 5, "for": 3, "geeksforgeeks": 13);

@debug map.remove($gfg, "geeks");
@debug map.remove($gfg, "geeks", "for");
@debug map.remove($gfg, "geek");
```

### 输出

```scss
("for": 3, "geeksforgeeks": 13)
("geeksforgeeks": 13)
("geeks": 5, "for": 3, "geeksforgeeks": 13)
```

## `map.values()`

此函数返回地图中所有值的逗号分隔列表。

### 语法

```scss
map.values($map)
map-values($map)
```

### 示例

```scss
$gfg: ("geeks": 5, "for": 3, "geeksforgeeks": 13);

@debug map.values($gfg);
```

### 输出

```scss
5, 3, 13
```