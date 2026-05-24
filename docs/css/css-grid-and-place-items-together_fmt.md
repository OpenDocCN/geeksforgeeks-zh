# CSS 网格和放置项目在一起

> 原文: [https://www.geeksforgeeks.org/css-grid-and-place-items-together/](https://www.geeksforgeeks.org/css-grid-and-place-items-together/)

在本文中，我们将看到如何使用 CSS 网格和 `place-items` 属性来排列网页中的元素。

`place-items` 不是专门为 `CSS 网格` 准备的，它也可以和其他属性一起使用。

**步骤:**

*   用类 `container` 创建三个 `div`
*   每个 `div` 将包含另外三个带有类 `box` 的 `div`。
*   将 `class` `initial` 添加到第一个 `div`，`middle` 添加到第二个 `div`，最后 `end` 添加到第三个 `div`。

## 代码示例

**HTML:**

```html
<!DOCTYPE html>
<html>
    <body>
        <h1>Place-items in start</h1>
        <!-- Container to be placed from starting -->
        <div class="container initial">
            <div class="box">Item 1</div>
            <div class="box">Item 2</div>
            <div class="box">Item 3</div>
        </div>
        <h1>Place-items in middle</h1>
        <!-- Container to be placed in middle -->
        <div class="container middle">
            <div class="box">Item 1</div>
            <div class="box">Item 2</div>
            <div class="box">Item 3</div>
        </div>
        <h1>Place-items in end</h1>
        <!-- Container to be placed in end -->
        <div class="container end">
            <div class="box">Item 1</div>
            <div class="box">Item 2</div>
            <div class="box">Item 3</div>
        </div>
    </body>
</html>
```

*   使用 CSS 网格将每个容器中的项目排列成三列。
*   添加属性 `place-items: start` 到 `div`，同样添加 `place-items: center` 和 `place-items: end` 到 `div`。

**CSS:**

```html
<style>
    h1 {
        text-align: center;
        margin-top: 10px;
    }
    /* arrange boxes of container in three column form*/
    .container {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
    }
    /* starting position for first container*/
    .initial {
        place-items: start;
    }
    /* middle position for second container*/
    .middle {
        place-items: center;
    }
    /* ending position for first container*/
    .end {
        place-items: end;
    }
    .box {
        width: 150px;
        height: 150px;
        display: flex;
        align-items: center;
        justify-content: center;
        background-color: #829099;
    }
</style>
```

**完整代码:**

```html
<!DOCTYPE html>
<html>
    <head>
        <style>
            h1 {
                text-align: center;
                margin-top: 10px;
            }
            /* arrange boxes of container
          in three column form*/
            .container {
                display: grid;
                grid-template-columns: 1fr 1fr 1fr;
            }
            /* starting position for first container*/
            .initial {
                place-items: start;
            }
            /* middle position for second container*/
            .middle {
                place-items: center;
            }
            /* ending position for first container*/
            .end {
                place-items: end;
            }
            .box {
                width: 150px;
                height: 150px;
                display: flex;
                align-items: center;
                justify-content: center;
                background-color: #829099;
            }
        </style>
    </head>
    <body>
        <h1>Place-items in start</h1>
        <!-- Container to be placed from starting -->
        <div class="container initial">
            <div class="box">Item 1</div>
            <div class="box">Item 2</div>
            <div class="box">Item 3</div>
        </div>
        <h1>Place-items in middle</h1>
        <!-- Container to be placed in middle -->
        <div class="container middle">
            <div class="box">Item 1</div>
            <div class="box">Item 2</div>
            <div class="box">Item 3</div>
        </div>
        <h1>Place-items in end</h1>
        <!-- Container to be placed in end -->
        <div class="container end">
            <div class="box">Item 1</div>
            <div class="box">Item 2</div>
            <div class="box">Item 3</div>
        </div>
    </body>
</html>
```

**输出:**

![](img/b33cd74027514ff360c59e0e9c16fc51.png)