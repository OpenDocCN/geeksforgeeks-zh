# 萨斯|萨斯:地图模块

> 原文:[https://www.geeksforgeeks.org/sass-sassmap-module/](https://www.geeksforgeeks.org/sass-sassmap-module/)

sass:map 模块提供了一些函数，这些函数可以查找与地图的键相关联的值。下面列出了一些主要功能:

*   **map.get():**
    This function returns the value associated with the the given key in the map. In case, no value is associated then it returns null.
    **Syntax:**

    ```html
    map.get(map, key)
    map-get(map, key) 
    ```

    **示例:**

    ```html
    $gfg: ("geeks": 5, "for": 3, "geeksforgeeks": 13)

    @debug map.get($gfg, "geeks")  
    @debug map.get($gfg, "GFG")  
    ```

    **输出:**

    ```html
    5
    null

    ```

*   **map.has-key():**
    此函数返回任何值是否与地图中的给定键相关联。它返回真或假。
    **语法:**

```html
map.has-key(map, key)
map-has-key(map, key) 
```

**示例:**

```html
$gfg: ("geeks": 5, "for": 3, "geeksforgeeks": 13)

@debug map.has-key($gfg, "geeks")  
@debug map.has-key($gfg, "GFG")  
```

**输出:**

```html
true
false

```

*   **map.keys():**
    This function returns a comma-separated list of all the keys in the map.
    **Syntax:**

    ```html
    map.keys(map)
    map-keys(map)
    ```

    **示例:**

    ```html
    $gfg: ("geeks": 5, "for": 3, "geeksforgeeks": 13)

    @debug map.keys($gfg) 
    ```

    **输出:**

    ```html
    "geeks", "for", "geeksforgeeks"

    ```

    *   **map.merge():**
    This function returns a new map with all the keys and value of both the given maps included. The function can also be used to add a new value or overrwrite a value in one map, by passing a single key/value pair as second map. If both maps have the same key, second map’s value takes precedence. All keys in the returned map that also appear in first map have the same order as they are. New keys from second map appear at the end of the map.
    **Syntax:**

    ```html
    map.merge(map1, map2)
    map-merge(map1, map2)
    ```

    **示例:**

    ```html
    $gfg: ("geeks": 5, "for": 3);
    $slash: ("geeksforgeeks": 13);

    @debug map.merge($gfg, $slash);

    @debug map.merge($gfg, ("geeksforgeeks": 20));

    @debug map.merge($gfg, ("geeks": 20));
    ```

    **输出:**

    ```html
    "geeks": 5, "for": 3, "geeksforgeeks":13
    "geeks": 5, "for": 3, "geeksforgeeks":20
    "geeks": 20, "for":3

    ```

    *   **map.remove():**
    This function returns a copy of the given map without the keys and associated value called in the function. Keys are ignored if no such key exist in the map.
    **Syntax:**

    ```html
    map.remove(map, keys)
    map-remove(map, keys)
    ```

    **示例:**

    ```html
    $gfg: ("geeks": 5, "for": 3, "geeksforgeeks": 13)

    @debug map.remove($gfg, "geeks") 
    @debug map.remove($gfg, "geeks", "for")
    @debug map.remove($gfg, "geek")  
    ```

    **输出:**

    ```html
    "for": 3, "geeksforgeeks":13
    "geeks": 5, "geeksforgeeks":13"
    geeks": 5, "for": 3, "geeksforgeeks":13

    ```

    *   **map.values():**
    This function returns a comma-separated list of all the values of the map.
    **Syntax:**

    ```html
    map.values(map)
    map-values(map)
    ```

    **示例:**

    ```html
    $gfg: ("geeks": 5, "for": 3, "geeksforgeeks": 13)

    @debug map.remove($gfg)  
    ```

    **输出:**

    ```html
    5 3 13

    ```