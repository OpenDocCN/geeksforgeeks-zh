# 如何在 HTML 内获取按钮切换状态？

> 原文:[https://www . geesforgeks . org/how-to-get-button-toggle-state-in-html/](https://www.geeksforgeeks.org/how-to-get-button-toggle-state-within-html/)

切换按钮基本上是**开/关**按钮。按钮可以从打开状态切换到关闭状态，反之亦然。这个过程叫做切换。
**切换按钮示例:**

*   我们配电盘上的按钮是切换按钮的最佳示例。
*   我们手机上的一些按钮——手电筒按钮、移动数据按钮、wifi 按钮、飞行模式、蓝牙按钮可以打开或关闭。这些都是切换按钮。

**方法:**
现在让我们看看如何在 Bootstrap 的帮助下用 HTML 设计这些按钮。
**示例 1:****默认**切换按钮
**HTML 代码(使用引导):**

## 超文本标记语言

```html
<div class="toggle">
    <div class="custom-control custom-switch">
      <input type="checkbox"
             class="custom-control-input"
             id="toggleSwitches">
      <label class="custom-control-label"
             for="toggleSwitches">
        TOGGLE</label>
    </div>
</div>
```

**风格使用 CSS:**

## 超文本标记语言

```html
<style>
        .toggle,
           {
           margin-top: 100px;
            font-size: 20px;
           }
           h1{
                color: green;
                font-size: 30px;
            }

</style>
```