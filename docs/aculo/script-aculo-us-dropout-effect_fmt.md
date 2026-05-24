# script.aculo.us DropOut 效应

> 原文: [https://www.geeksforgeeks.org/script-aculo-us-dropout-effect/](https://www.geeksforgeeks.org/script-aculo-us-dropout-effect/)

`script.aculo.us` 的 `DropOut()` 方法用于从 DOM 中移除并显示元素，以模拟下拉效果。核心效应，`Effect.MoveBy()` 和 `Effect.Opacity()` 组合在一起使 **DropOut** 效果。可以和 `Effect.Appear()` 一起实现删除元素，然后再次显示。

## 语法

```
new Effect.DropOut(element_id, {options});
```

这种效果不需要任何特定的参数。可以使用视觉效果模块的常用参数。

## 示例

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
            new Effect.Appear(element, { duration: 1 });
        }

        function HideElement(element) {
            new Effect.DropOut(element, { duration: 3 });
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

## 输出

![](img/64e96c3e17603c16a020c313bb86b002.png)