# 如何在 HTML5 中预加载一个音频？

> 原文：[https://www.geeksforgeeks.org/how-to-preload-an-audio-in-html5/](https://www.geeksforgeeks.org/how-to-preload-an-audio-in-html5/)

在本文中，我们将用 HTML 预加载音频。我们使用 `preload="auto"` 属性来预加载音频文件。HTML `audio` 元素的 `preload` 属性用于指定页面加载时作者认为应该如何加载音频。`audio` 元素的 `preload` 属性允许作者向浏览器指示应该如何实现网站的用户体验。在某些情况下，这个属性可以忽略。

你要知道 [HTML `<audio>` 预加载属性](https://www.geeksforgeeks.org/html-audio-preload-attribute/)

**注意：** 如果 `autoplay` 属性存在，则 `preload` 属性被忽略。

以下是说明使用 `preload` 属性的示例。

**示例 1：** 当 `preload="auto"` 时

### HTML

```html
<!DOCTYPE html>
<html>
<body>
  <h1>GFG</h1>
  <p>Hit the button for audio</p>
  <audio controls preload="auto">
     <source src="gfg.ogg" type="audio/ogg">
     <source src="gfg.mp3" type="audio/mpeg">
  </audio>
</body>
</html>
```

**输出：**

![](img/2cd9b1533a0eb16126e2e2e5c250a083.png)

例 1

**示例 2：** 当 `preload="none"` 时

### HTML

```html
<!DOCTYPE html>
<html>
<body>
  <h1>GFG</h1>
  <p>Hit the button for audio</p>
  <audio controls preload="none">
     <source src="gfg.ogg" type="audio/ogg">
     <source src="gfg.mp3" type="audio/mpeg">
  </audio>
</body>
</html>
```

**输出：**

![](img/cf43b0ac3fe228534ae21bc0595b1d78.png)

例 2