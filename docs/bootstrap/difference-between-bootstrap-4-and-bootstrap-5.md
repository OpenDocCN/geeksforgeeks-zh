# 自举 4 和自举 5 的区别

> 原文:[https://www . geeksforgeeks . org/bootstrap-4 和 bootstrap-5 的区别/](https://www.geeksforgeeks.org/difference-between-bootstrap-4-and-bootstrap-5/)

**什么是自举？**

这是一个从 2011 年末开始的开源框架，用于以移动优先的方式更快更容易地设计响应性网站。引导可用于 HTML、CSS 和 JS。根据服务器端语言如 PHP、Node 等。bootstrap 有助于设计前端。Bootstrap 通过准备好模板使开发人员的工作变得更容易，模板是每个网站的基本部分。因此，人们倾向于进一步开发，而不会浪费时间在具有漂亮设计和响应能力的基本模板上。

**为什么自举？**

*   更快更容易
*   移动第一风格
*   它是免费的！可在<u>www.getbootstrap.com</u>获得
*   浏览器支持
*   响应性设计

Bootstrap 5 alpha 于 2020 年 6 月中旬推出。就像在 alpha-1 版本中一样，未来可以在 bootstrap 5 中添加更多的特性

在引导数据库 5 的 alpha-1 版本中，删除了以下一些类:

*   表格–行
*   表单–内嵌
*   列表–内嵌
*   卡片组

一些添加的类:

*   **gx-*** (类控制水平/柱槽宽度)
*   **gy-*** (类控制垂直/行檐槽宽度)
*   **g-*** (类控制水平&垂直檐槽宽度)
*   行-列-自动

**Bootstrap 4 与 Bootstrap 5 的区别**

<figure class="table">

| 的基础 | 自举 4 | 自举 5 |
| --- | --- | --- |
| **Grid system** | 是吴仪(xs、sm、md、lg、xl))。 | 376(xs(sm)MD(LG)XL(XXV)l)号文件。 |
| **color** | Its color is limited. | Additional colors are added to the appearance, and A card improves the palette. There are various shades to choose from. |
| **Jquery** | It has Jquery and all related plug-ins. | Jquery was removed and switched to vanilla JS with some work plug-ins. |
| **互联网浏览器** | Bootstrap 4 supports both IE 10 and IE 11. | Bootstrap 5 does not support IE 10 and 11. |
| **Form element** | Radio buttons and check boxes have different appearances in different OS and browsers. The form uses whatever the default browser provides. | On different operating systems or browsers, the appearance of form elements will not change. Forms can be customized and form controls can be added. They are independent of browsers. |
| **公用设施空气污染指数** | We can't modify Utilities in bootstrap 4. | Bootstrap 5 gives us the freedom to modify and also creates our own utility. |
|  | We use. The px we use | 字体大小的胶子.带有 rem 字体大小的 g * |
| **Vertical category** | Columns can be positioned relative to each other | Columns cannot be positioned relative to each other. |
| **自举图标** | Bootstrap 4 doesn't have its own SVG icon, so we have to use fonts-awesome icons. | Bootstrap 5 has its own SVG icon. |
| **巨观宝座** | 。 | Big screen is not supported. |
| **deck** | Card deck is used to create a set of cards with equal width and height. | Card class was removed in bootstrap. |
| **无酒吧** | We have the inline -block attribute, and we will get the white drop-down menu as the default value of the drop-down menu-dark class. | The inline block attribute has been removed, and we will get the black drop-down menu as the default value of the drop-down menu-dark class. |
| **Static site generator** | 自举 4 使用了吉基尔博士软件。 | Bootstrap 5 uses Hugo software because it is a fast static site generator. |
| flexbox 网格 | This makes vertical design easier to implement, and columns and rows are also easy to implement. According to the demand, you can directly use the content of the class adjustment center to adjust. | Advanced grid system is available, and the same column has no relative position. |

</figure>