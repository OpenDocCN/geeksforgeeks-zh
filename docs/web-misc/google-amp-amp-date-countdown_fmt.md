# 谷歌 AMP-AMP-date-倒计时

> 原文: [https://www.geeksforgeeks.org/google-amp-amp-date-countdown/](https://www.geeksforgeeks.org/google-amp-amp-date-countdown/)

![](img/9f4c77d78e00cf75fc29323762067dd8.png)

`amp-date-countdown`是用来倒数到一个特定的日期，这是渲染到 AMP HTML 页面。它专门用作计时器或倒计时。

## 必需脚本

添加`amp-date-countdown`组件。

```html
<script async custom-element="amp-date-countdown" src=
"https://cdn.ampproject.org/v0/amp-date-countdown-0.1.js">
</script>
```

添加`amp-mustache`组件。

```html
<script async custom-template="amp-mustache" src=
"https://cdn.ampproject.org/v0/amp-mustache-0.2.js">
</script>
```

## 属性

1.  `enddate`: 是 ISO 规定的倒计时日期。
2.  `timeleft-ms`: 毫秒值倒计时。
3.  `offset-seconds`: 要添加到结束日期的数字。可能是积极的，也可能是消极的。
4.  `biggest-unit`: 该属性可以设置为`days`、`hours`、`minutes`、`seconds`(默认:`days`)。未显示大于用户定义单位的单位。如果还剩 2 天，最大单位是小时，它显示还剩 48 小时。
5.  `locale`: 设置定时器显示的语言。

| 英语 | en |
| :--- | :--- |
| 德国人 | de |
| 西班牙语 | es |
| 法语 | fr |
| 意大利的 | it |
| 日本人 | ja |
| 荷兰人 | nl |
| 韩国的 | ko |
| 俄语 | ru |
| 越南人 | vi |
| 土耳其的 | tr |
| 葡萄牙语 | pt |
| 泰国的 | th |
| 简体/繁体中文 | zh-cn/zh-tw |

## 示例

```html
<!doctype html>
<html amp>

<head>
    <meta charset="utf-8">
    <title>Google AMP amp-date-countdown</title>

    <!-- Include the `amp-date-countdown` component ... -->
    <script async custom-element="amp-date-countdown" src=
        "https://cdn.ampproject.org/v0/amp-date-countdown-0.1.js">
    </script>

    <!-- Include the `amp-mustache` component ... -->
    <script async custom-template="amp-mustache" src=
        "https://cdn.ampproject.org/v0/amp-mustache-0.2.js">
    </script>

    <meta name="viewport" content=
        "width=device-width,minimum-scale=1,initial-scale=1">

    <link rel="canonical" href=
        "https://amp.dev/documentation/examples/components/amp-date-countdown/index.html">

    <style amp-boilerplate>
        body {
            -webkit-animation: -amp-start 8s steps(1, end) 0s 1 normal both;
            -moz-animation: -amp-start 8s steps(1, end) 0s 1 normal both;
            -ms-animation: -amp-start 8s steps(1, end) 0s 1 normal both;
            animation: -amp-start 8s steps(1, end) 0s 1 normal both
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
    <script async src="https://cdn.ampproject.org/v0.js"></script>

    <style amp-custom>
        amp-date-countdown {
            display: block;
        }
    </style>
</head>

<body>
    <amp-date-countdown timestamp-seconds="2147483648" locale="en" layout="fixed-height" height="100">
        <template type="amp-mustache">
            {{d}} {{days}}, {{h}} {{hours}}, {{m}} {{minutes}}, {{s}} {{seconds}}
        </template>
    </amp-date-countdown>

    <amp-date-countdown timestamp-seconds="2147483648" biggest-unit="minutes" layout="fixed-height" height="100">
        <template type="amp-mustache">
            {{m}} minutes and {{s}} seconds until
            <a href="https://en.wikipedia.org/wiki/Year_2038_problem">Y2K38</a>
        </template>
    </amp-date-countdown>
</body>

</html>
```

## 输出

![](img/8397e26791ade86b86e162920383099d.png)