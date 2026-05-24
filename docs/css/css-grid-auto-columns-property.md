# CSS |网格-自动列属性

> 原文:[https://www . geesforgeks . org/CSS-grid-auto-columns-property/](https://www.geeksforgeeks.org/css-grid-auto-columns-property/)

CSS 中的**网格自动列**属性用于指定隐式生成的网格容器的列大小。

**语法:**

```html
grid-auto-columns: auto|max-content|min-content|length|
percentage|minmax(min, max)|initial|inherit;
```

**属性值:**

*   **auto:** It is the default value. The size is determined implicitly according to the size of the container.

    **例 1:**

    ```html
    <!DOCTYPE html> 
    <html> 
        <head> 
            <title> 
                CSS grid-auto-column Property 
            </title> 

            <style> 
                .main { 
                    display: grid; 
                    grid-template-areas: "a a"; 
                    grid-gap: 20px; 
                    padding: 30px; 
                    background-color: green;
                    grid-auto-columns:  auto;

                } 
                .GFG { 
                    text-align: center; 
                    font-size: 35px; 
                    background-color: white; 
                    padding: 20px 0; 
                } 
            </style> 
        </head> 

        <body> 
            <div class = "main"> 
                <div class = "GFG">1</div> 
                <div class = "GFG">2</div> 
                <div class = "GFG">3</div> 
                <div class = "GFG">4</div> 
                <div class = "GFG">5</div> 
            </div> 
        </body> 
    </html> 
    ```

    **输出:**
    ![](img/00ec870aa9e76e2e8994b7febad834fa.png)

*   **length:** It is used to specify the size as integer length. Negative values are not allowed.

    **示例:**

    ```html
    <!DOCTYPE html> 
    <html> 
        <head> 
            <title> 
                CSS grid-auto-column Property 
            </title> 

            <style> 
                .main { 
                    display: grid; 
                    grid-template-areas: "a a"; 
                    grid-gap: 20px; 
                    padding: 30px; 
                    background-color: green;
                    grid-auto-columns: 8.5cm;

                } 
                .GFG { 
                    text-align: center; 
                    font-size: 35px; 
                    background-color: white; 
                    padding: 20px 0; 
                } 
            </style> 
        </head> 

        <body> 
            <div class = "main"> 
                <div class = "GFG">1</div> 
                <div class = "GFG">2</div> 
                <div class = "GFG">3</div> 
                <div class = "GFG">4</div> 
                <div class = "GFG">5</div> 
            </div> 
        </body> 
    </html> 
    ```

    **输出:**
    ![](img/2422e7f72214a72d06ab748888fadfaa.png)

*   **percentage:** It specifies the size as percentage value.

    **示例:**

    ```html
    <!DOCTYPE html> 
    <html> 
        <head> 
            <title> 
                CSS grid-auto-column container Property 
            </title> 

            <style> 
                .main { 
                    display: grid; 
                    grid-template-areas: "a a"; 
                    grid-gap: 20px; 
                    padding: 30px; 
                    background-color: green;
                    grid-auto-columns:  30%;

                } 
                .GFG { 
                    text-align: center; 
                    font-size: 35px; 
                    background-color: white; 
                    padding: 20px 0; 
                } 
            </style> 
        </head> 

        <body> 
            <div class = "main"> 
                <div class = "GFG">1</div> 
                <div class = "GFG">2</div> 
                <div class = "GFG">3</div> 
                <div class = "GFG">4</div> 
                <div class = "GFG">5</div> 
            </div> 
        </body> 
    </html> 
    ```

    **输出:**
    ![](img/e8b4df168f15e9e8c39be23fe744171b.png)

*   **最大含量:**它根据容器中最大的物品来指定尺寸。
*   **最小含量:**根据容器中最小的物品指定尺寸。
*   **minmax(min, max):** It specifies the size in the range of [min, max]. greater than or equal to min and less than or equal to max.

    **示例:**

    ```html
    <!DOCTYPE html> 
    <html> 
        <head> 
            <title> 
                CSS grid-auto-column Property 
            </title> 

            <style> 
                .main { 
                    display: grid; 
                    grid-template-areas: "a a"; 
                    grid-gap: 20px; 
                    padding: 30px; 
                    background-color: green;
                    grid-auto-columns:  minmax(100px, 4cm);

                } 
                .GFG { 
                    text-align: center; 
                    font-size: 35px; 
                    background-color: white; 
                    padding: 20px 0; 
                } 
            </style> 
        </head> 

        <body> 
            <div class = "main"> 
                <div class = "GFG">1</div> 
                <div class = "GFG">2</div> 
                <div class = "GFG">3</div> 
                <div class = "GFG">4</div> 
                <div class = "GFG">5</div> 
            </div> 
        </body> 
    </html> 
    ```

    **输出:**
    ![](img/7b9cc66a6541de13fe4e6ffa293e3fd4.png)

*   **initial:** It sets the grid-auto-columns property to its default value.

    **示例:**

    ```html
    <!DOCTYPE html> 
    <html> 
        <head> 
            <title> 
                CSS grid-auto-column Property 
            </title> 

            <style> 
                .main { 
                    display: grid; 
                    grid-template-areas: "a a"; 
                    grid-gap: 20px; 
                    padding: 30px; 
                    background-color: green;
                    grid-auto-columns: initial;

                } 
                .GFG { 
                    text-align: center; 
                    font-size: 35px; 
                    background-color: white; 
                    padding: 20px 0; 
                } 
            </style> 
        </head> 

        <body> 
            <div class = "main"> 
                <div class = "GFG">1</div> 
                <div class = "GFG">2</div> 
                <div class = "GFG">3</div> 
                <div class = "GFG">4</div> 
                <div class = "GFG">5</div> 
            </div> 
        </body> 
    </html> 
    ```

    **输出:** ![](img/ed8ad4c4a26201ceafdbaa66883d4170.png)

*   **inherit:** It sets the grid-auto-columns property from its parent element.

    **示例:**

    ```html
    <!DOCTYPE html> 
    <html> 
        <head> 
            <title> 
                CSS grid-auto-column Property 
            </title> 

            <style> 
                .main { 
                    display: grid; 
                    grid-template-areas: "a a"; 
                    grid-gap: 20px; 
                    padding: 30px; 
                    background-color: green;
                    grid-auto-columns:  inherit;

                } 
                .GFG { 
                    text-align: center; 
                    font-size: 35px; 
                    background-color: white; 
                    padding: 20px 0; 
                } 
            </style> 
        </head> 

        <body> 
            <div class = "main"> 
                <div class = "GFG">1</div> 
                <div class = "GFG">2</div> 
                <div class = "GFG">3</div> 
                <div class = "GFG">4</div> 
                <div class = "GFG">5</div> 
            </div> 
        </body> 
    </html> 
    ```

    **输出:** ![](img/ed8ad4c4a26201ceafdbaa66883d4170.png)

**支持的浏览器:***网格自动列属性*支持的浏览器如下:

*   Chrome 57.0
*   Edge 16.0
*   Firefox 52.0
*   Safari 10.0
*   Opera 44.0