# 谷歌 `amp-twitter`

> 原文: [https://www.geeksforgeeks.org/google-amp-amp-twitter/](https://www.geeksforgeeks.org/google-amp-amp-twitter/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

推特已经成为一种交流思想和新闻的现代方式，可以使用嵌入推特推文的 `amp-twitter` 轻松嵌入 `AMP HTML` 页面。

## 必需脚本

将 `amp-twitter` 组件导入标题。

```html
<script async custom-element="amp-twitter" 
    src="https://cdn.ampproject.org/v0/amp-twitter-0.1.js">
</script>
```

## 属性

*   `data-tweet-id`: 同 `data-timelines` 或 `data-timeline-source-type`。这是一条推特的 id。例如 – `1009149991452135424`。
*   `data-timeline`: 将显示 `AMP` 推特账号的时间线。

## 示例

### 超文本标记语言

```html
<!doctype html>
<html ⚡>

<head>
    <meta charset="utf-8">
    <title>Google AMP amp-twitter</title>

    <script async src="https://cdn.ampproject.org/v0.js">
    </script>

    <!-- Don't forget to import the twitter component -->
    <script async custom-element="amp-twitter" 
        src="https://cdn.ampproject.org/v0/amp-twitter-0.1.js">
    </script>

    <link rel="canonical" href="https://amp.dev/documentation/examples/components/amp-twitter/index.html">

    <meta name="viewport" content="width=device-width,minimum-scale=1,initial-scale=1">

    <style amp-boilerplate>
        body {
            -webkit-animation: -amp-start 8s steps(1, end) 0s 1 normal both;
            -moz-animation: -amp-start 8s steps(1, end) 0s 1 normal both;
            -ms-animation: -amp-start 8s steps(1, end) 0s 1 normal both;
            animation: -amp-start 8s steps(1, end) 0s 1 normal both;
        }

        @-webkit-keyframes -amp-start {
            from { visibility: hidden }
            to { visibility: visible }
        }

        @-moz-keyframes -amp-start {
            from { visibility: hidden }
            to { visibility: visible }
        }

        @-ms-keyframes -amp-start {
            from { visibility: hidden }
            to { visibility: visible }
        }

        @-o-keyframes -amp-start {
            from { visibility: hidden }
            to { visibility: visible }
        }

        @keyframes -amp-start {
            from { visibility: hidden }
            to { visibility: visible }
        }
    </style>

    <noscript>
        <style amp-boilerplate>
            body {
                -webkit-animation: none;
                -moz-animation: none;
                -ms-animation: none;
                animation: none
            }
        </style>
    </noscript>
</head>

<body>
    <amp-twitter width="375" height="472" 
        layout="responsive" 
        data-tweetid="1307176901916516354">
    </amp-twitter>

    <amp-twitter width="390" height="330" 
        layout="responsive" 
        data-tweetid="1307176901916516354" 
        data-cards="hidden">
    </amp-twitter>
</body>

</html>
```

## 输出

![](img/2cf851aac577ee2ed0294641e7ddee2a.png)

第一 `amp-twitter` 组件的输出

![](img/2f74436aca477dd92f9c7e26d9aedef9.png)

第二 `amp-twitter` 组件的输出