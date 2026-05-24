# SASS |地图功能

> 原文:[https://www.geeksforgeeks.org/sass-map-functions/](https://www.geeksforgeeks.org/sass-map-functions/)

SASS 映射数据类型用于显示一个或多个键值对。除了下面列表中显示的地图功能，您还可以对地图使用任何 SASS 列表功能。

以下列表包含了 SASS 中的所有地图功能:

1.  **map-has-key($map，$key)函数:**该函数返回一个布尔值，检查给定的地图是否包含给定的键。
    *   **例:**

        ```html
        map-has-key(("red": #ff0000, "yellow": #ffff00), blue)
        ```

    *   **输出:**

        ```html
        false
        ```

2.  **map-merge($map1，$map2)函数:**该函数返回一个包含$map2 的地图，该地图连接到$map1 的末尾。
    *   **例:**

        ```html
        map-merge(("red": #ff0000, "yellow": #ffff00), ("blue": #0000ff)
        ```

    *   **输出:**

        ```html
        ("red": #ff0000, "yellow": #ffff00, "blue": #0000ff)
        ```

3.  **地图键($map)功能:**该功能返回给定地图中的键列表。
    *   **例:**

        ```html
        map-keys(("red": #ff0000, "yellow": #ffff00))
        ```

    *   **输出:**

        ```html
        ("red", "yellow")
        ```

4.  **map-remove($map，$keys)函数:**该函数返回没有给定按键的地图。
    *   **例:**

        ```html
        map-remove(("red": #ff0000, "yellow": #ffff00), "red")
        ```

    *   **输出:**

        ```html
        ("yellow": #ffff00)
        ```

5.  **map-values($map)函数:**该函数返回给定地图中的值列表。
    *   **例:**

        ```html
        map-values(("red": #ff0000, "yellow": #ffff00))
        ```

    *   **输出:**

        ```html
        (#ff0000, #ffff00)
        ```

6.  **map-get($map，$key)函数:**该函数返回与给定键关联的值。
    *   **例:**

        ```html
        map-get(("blue": #0000ff, "yellow": #ffff00), "blue")
        ```

    *   **输出:**

        ```html
        #0000ff
        ```