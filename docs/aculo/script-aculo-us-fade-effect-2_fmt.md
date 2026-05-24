# 脚本.aculo.us 淡入淡出效果

> 原文：[https://www.geeksforgeeks.org/script-aculo-us-fade-effect-2/](https://www.geeksforgeeks.org/script-aculo-us-fade-effect-2/)

可以使用`script.aculo.us`的`Effect.Fade()`方法从DOM中淡出。`Effect.Fade()`可配合`Effect.Appear()`方法淡入淡出内容后再显示。

## 语法：

```
new Effect.Fade(id_of_element, [options]);
```

这种效果没有任何特定的参数。可以使用视觉效果模块的通用参数。

## 示例：

```
<!DOCTYPE html>
<html>

<head>

<script type="text/javascript" 
        src="prototype.js">
    </script>

<script type="text/javascript" 
        src="scriptaculous.js">
    </script>

<script type="text/javascript">
        function ShowElement(element) {
            new Effect.Appear(element, 
                { duration: 1 });
        }

function HideElement(element) {
            new Effect.Fade(element, 
            { duration: 1, from: 1.0, to: 0 });
        }
    </script>
</head>

<body>
    <div onclick="ShowElement('element')">
        <Button>Show Content</Button>
    </div>
    <br />

<div onclick="HideElement('element')">
        <Button>Hide Content</Button>
    </div>
    <br />
    <img id="element" src="GEEKSIMAGES/gfg.png">
</body>

</html>
```

### 输出：
![](img/2fb5ed46fba35e175c0fae48bda61793.png)