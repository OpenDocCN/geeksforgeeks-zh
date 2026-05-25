# 如何使用 JavaScript 将语音转换为文本？

> 原文：[https://www.geeksforgeeks.org/how-to-convert-speech-into-text-using-javascript/](https://www.geeksforgeeks.org/how-to-convert-speech-into-text-using-javascript/)

在本文中，我们将学习使用 HTML 和 JavaScript 将语音转换为文本。

方法：我们添加了一个内容可编辑的 `div`，通过它我们可以编辑任何 HTML 元素。

## HTML 代码

```html
<div class="words" contenteditable>
    <p id="p"></p>
</div>
```

我们使用 `SpeechRecognition` 对象将语音转换为文本，然后在屏幕上显示文本。

我们还增加了 `webkitSpeechRecognition` 以在谷歌 Chrome 和苹果 Safari 中进行语音识别。

## JavaScript 代码

```javascript
window.SpeechRecognition = window.SpeechRecognition
    || window.webkitSpeechRecognition;
```

`interimResults` 属性应返回 `true`，默认值为 `false`。如此设置：`interimResults = true`。

## JavaScript 代码

```javascript
recognition.interimResults = true;
```

使用 `appendChild()` 方法追加一个节点作为节点的最后一个子节点。

## JavaScript 代码

```javascript
const words = document.querySelector('.words');
words.appendChild(p);
```

添加 `addEventListener`，在这个事件监听器中，`map()` 方法用于创建一个新数组，结果是为每个数组元素调用一个函数。

注：此方法不改变原数组。

使用 `join()` 方法将数组作为字符串返回。

## JavaScript 代码

```javascript
recognition.addEventListener('result', e => {
    const transcript = Array.from(e.results)
        .map(result => result[0])
        .map(result => result.transcript)
        .join('')

    document.getElementById("p").innerHTML = transcript;
    console.log(transcript);
});
```

最终代码：

## HTML 代码

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">

    <title>Speech to Text</title>
</head>

<body>
    <div class="words" contenteditable>
        <p id="p"></p>
    </div>

    <script>
        var speech = true;
        window.SpeechRecognition = window.SpeechRecognition
                        || window.webkitSpeechRecognition;

        const recognition = new SpeechRecognition();
        recognition.interimResults = true;
        const words = document.querySelector('.words');
        words.appendChild(p);

        recognition.addEventListener('result', e => {
            const transcript = Array.from(e.results)
                .map(result => result[0])
                .map(result => result.transcript)
                .join('')

            document.getElementById("p").innerHTML = transcript;
            console.log(transcript);
        });

        if (speech == true) {
            recognition.start();
            recognition.addEventListener('end', recognition.start);
        }
    </script>
</body>

</html>
```

输出：

如果用户在运行文件后说“Hello World”，它会在屏幕上显示以下内容。

```text
Hello World
```