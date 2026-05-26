# Web 振动 API：`navigator.vibrate()` 方法

> 原文：[https://www.geeksforgeeks.org/web-vibration-api-navigator-vibrate-method/](https://www.geeksforgeeks.org/web-vibration-api-navigator-vibrate-method/)

`navigator.vibrate()` 方法使用设备上的振动硬件（如果存在这样的硬件）。如果设备不支持振动，那么调用此方法将不会产生任何效果。如果调用此方法时振动模式已经开始，则之前的模式将停止，而新的模式将开始。

如果我们在方法中放入无效的参数，那么它将不会振动，并且它将返回 `false`，否则它将返回 `true`。如果振动模式过长，那么它就会被截断。最大长度取决于具体实现。

## 语法

```html
var successBool = window.navigator.vibrate(pattern);
```

## 参数

该方法接受单参数 `pattern`，为振动和暂停间隔提供模式。振动值和间隔值都是交替的，并且值以毫秒为单位。我们可以提供单个值或一组值。将 `0`、空数组或全零数组作为参数传递将会取消任何当前正在进行的振动。

## 返回值

成功返回 `true`，否则返回 `false`。

下面的例子说明了 Web 振动 API 中的 `navigator.vibrate()` 方法：

### 示例 1

```html
// To check that is vibration API supported
if (navigator.vibrate) {
    window.navigator.vibrate(200);
}
```

**输出：**

```html
Vibrates for 200 milliseconds
```

### 示例 2

```html
// To check that is vibration API supported
if (navigator.vibrate) {
    window.navigator.vibrate(0);
}
```

**输出：**

```html
Will cancel any currently ongoing vibration pattern
```

### 示例 3

```html
// To check that is vibration API supported
if (navigator.vibrate) {
    window.navigator.vibrate([100, 30, 100, 30, 100, 30, 200,
                         30, 200, 30, 200, 30, 100, 30, 100, 30, 100]);
}
```

**输出：**

```html
Vibrate 'SOS' in Morse
```

## 支持的浏览器

Web 振动 API `navigator.vibrate()` 方法支持的浏览器如下：

*   Google Chrome 32 或以上
*   Firefox 16 或更高版本