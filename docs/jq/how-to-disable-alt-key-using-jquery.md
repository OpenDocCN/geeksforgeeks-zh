# 如何使用 jQuery 禁用 ALT 键？

> 原文:[https://www . geesforgeks . org/如何禁用-alt-key-use-jquery/](https://www.geeksforgeeks.org/how-to-disable-alt-key-using-jquery/)

jQuery 是一个快速、小型且功能丰富的 JavaScript 库。它通过一个易于使用的跨多种浏览器工作的应用编程接口，使 HTML 文档遍历和操作、事件处理、动画和 Ajax 变得更加简单

**有什么用？**

当你踏入网络开发领域时，禁用 ALT 键有着广泛的应用

一些常用的 ALT 快捷键有:

*   **ALT + backarrow:** 用于返回，它的应用主要出现在你的应用在全屏里面，导航关闭的时候，就像在全屏一样。
*   **ALT + Frontarrow:** 用于返回，它的应用主要出现在你的应用在全屏里面，导航关闭的时候，就像在全屏一样。

**方法:**在您想要插入的任何页面、函数或脚本标签中，插入一个小函数，该函数基本上利用了 jQuery 内置的按键功能。

当用户按下键盘上的某个键时，向下键事件被发送到某个元素。如果按键保持按下状态，则每次操作系统重复按键时都会发送事件。它可以附加到任何元素，但事件只发送到具有焦点的元素。

**语法:**

```html
$(selector).keydown(function)
```

**返回值:**按下特定键的键码。

**例 1:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <h1 id="submission">GeeksforGeeks</h1>
    <script>
        document.onkeydown = function (evt) {

            // Keycode of alt is 18
            if (evt.keyCode == 18) {
                evt.preventDefault();

                document.getElementById(
                    "submission").click();
            }
        }
    </script>
</head>

</html>
```

**输出:**

```html
NO shortcuts using ALT will work in your current HTML page.
```

**例 2:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <script language="javascript" type="text/javascript">
        function getKeyCodeEvent(ev) {
            var code = (document.all) ?
                event.keyCode : ev.which;

            var alt = (document.all) ?
                event.altKey :
                ev.modifiers & Event.ALT_MASK;

            if (document.all) {

                // Example ALT+F4
                if (alt && code == 115) {
                    try {
                        // Your requirements
                    } catch (e) {
                    }
                }
            }
        }
    </script>
</head>

</html>
```

**输出:**

```html
NO shortcuts  using ALT will work in your current HTML page.
```