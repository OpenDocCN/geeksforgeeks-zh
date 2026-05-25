# jQuery | 隐藏/显示、切换和淡入淡出方法示例

> 原文: [https://www.geeksforgeeks.org/jquery-hideshow-toggle-fading-methods-examples/](https://www.geeksforgeeks.org/jquery-hideshow-toggle-fading-methods-examples/)

jQuery 提供了一个非常简单的界面来实现各种惊人的效果。jQuery 方法允许我们用最少的配置快速应用常用的效果。

## jQuery `hide()` 和 `show()`

### jQuery `hide()`
隐藏要隐藏的语法或 html 元素。

```html
$(selector).hide(speed, callback);
```

### jQuery `show()`
显示您希望用户看到的语法或 html 元素。

```html
$(selector).show(speed, callback);
```

对于上述两种语法，`speed` 参数是一个可选参数，用于定义隐藏和显示 html 内容的速度。可以使用预定义字符串 `"slow"` 或 `"fast"` 中的一个来指定持续时间，或者以毫秒为单位来指定持续时间，以获得更高的精度；较高的值表示较慢的动画。
`callback` 参数是隐藏和显示功能完成后使用的可选参数。

**示例:**
![](img/ccd6debc5ac8f6d5cf9b2d820038e7f7.png)

`hide()` 方法只是设置内联样式 `display: none` 所选元素。相反，`show()` 方法将匹配的元素集的显示属性恢复到内联样式显示之前的初始状态，通常是 `block`、`inline` 或 `inline-block`。

**输出:**

<video class="wp-video-shortcode" id="video-199634-1" width="490" height="196" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/1.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/1.webm](https://media.geeksforgeeks.org/wp-content/uploads/1.webm)</video>

### `speed` 参数示例

**示例 1:**
![](img/8d7c409d3dbb1d08a50f78124af3d005.png)

**输出:**
<video class="wp-video-shortcode" id="video-199634-2" width="490" height="196" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/2.webm?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/2.webm](https://media.geeksforgeeks.org/wp-content/uploads/2.webm)</video>

**示例 2:**
![](img/6b1ce53db2075183e97b758df410a0ac.png)

**输出:**
<video class="wp-video-shortcode" id="video-199634-3" width="490" height="196" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/3.webm?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/3.webm](https://media.geeksforgeeks.org/wp-content/uploads/3.webm)</video>

## jQuery `toggle()`

jQuery `toggle()` 方法以这样一种方式显示或隐藏元素：如果元素最初被显示，它将被隐藏；如果隐藏，它将被显示。

**语法:**

```html
$(selector).toggle(speed, callback);
```

`speed` 和 `callback` 参数是与前一个相同的可选参数。

**示例:**
![](img/c8d43032d3031ccfd2e8034467edd855.png)

**输出:**

<video class="wp-video-shortcode" id="video-199634-4" width="490" height="196" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/4.webm?_=4">[https://media.geeksforgeeks.org/wp-content/uploads/4.webm](https://media.geeksforgeeks.org/wp-content/uploads/4.webm)</video>

## jQuery 淡入淡出方法

在 jQuery 的帮助下，您可以根据需要淡入或淡出 HTML 元素。以下是淡入淡出的方法：

### 1. jQuery `fadeIn()` 方法
**语法:**

```html
$(selector).fadeIn(speed, callback);
```

`fadeIn()` 功能用于在 HTML 中显示一个隐藏的元素。可选参数 `speed` 用于控制淡入的速度，第二个可选参数 `callback` 在淡入完成后使用。

**示例:**
![](img/c789ef2a9b0a1e5014d0febbbfff4885.png)

**输出:**
<video class="wp-video-shortcode" id="video-199634-5" width="336" height="288" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/6.webm?_=5">[https://media.geeksforgeeks.org/wp-content/uploads/6.webm](https://media.geeksforgeeks.org/wp-content/uploads/6.webm)</video>

### 2. jQuery `fadeOut()` 方法
**语法:**

```html
$(selector).fadeOut(speed, callback);
```

`fadeOut()` 功能用于淡出（隐藏）HTML 中的一个元素。可选参数 `speed` 用于控制淡出的速度，第二个可选参数 `callback` 在淡出完成后使用。

**示例:**
![](img/5a61cecf539d548a788f0b762f4fdae1.png)

**输出:**
<video class="wp-video-shortcode" id="video-199634-6" width="336" height="288" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/7.webm?_=6">[https://media.geeksforgeeks.org/wp-content/uploads/7.webm](https://media.geeksforgeeks.org/wp-content/uploads/7.webm)</video>

### 3. jQuery `fadeToggle()` 方法
**语法:**

```html
$(selector).fadeToggle(speed, callback);
```

`fadeToggle()` 功能用于在 `fadeIn()` 和 `fadeOut()` 之间切换。

**示例:**
![](img/40fa373a22fd9adec1079c6ed084728b.png)

**输出:**
<video class="wp-video-shortcode" id="video-199634-7" width="336" height="288" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/8.webm?_=7">[https://media.geeksforgeeks.org/wp-content/uploads/8.webm](https://media.geeksforgeeks.org/wp-content/uploads/8.webm)</video>

### 4. jQuery `fadeTo()` 方法
**语法:**

```html
$(selector).fadeTo(speed, opacity, callback);
```

`fadeTo()` 功能允许将元素淡化到给定的不透明度（0 到 1 之间的范围），`opacity` 是填充该功能的必需字段。可选参数 `speed` 用于控制动画的速度，第二个可选参数 `callback` 在淡入淡出完成后使用。

**示例:**
![](img/dfdfcee29a9e8609cdd48146a97416d0.png)

**输出:**
<video class="wp-video-shortcode" id="video-199634-8" width="336" height="288" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/81.webm?_=8">[https://media.geeksforgeeks.org/wp-content/uploads/81.webm](https://media.geeksforgeeks.org/wp-content/uploads/81.webm)</video>