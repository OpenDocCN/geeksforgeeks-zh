# SVG `<animateTransform>`元素

> 原文:[https://www.geeksforgeeks.org/svg-animatetransform-element/](https://www.geeksforgeeks.org/svg-animatetransform-element/)

SVG 代表可缩放矢量图形。它定义了基于矢量的图形和动画，就像在 HTML 画布中一样。

animateTransform 元素在其目标元素上设置变换属性的动画，从而允许动画控制平移、缩放、旋转和/或倾斜。

**语法:**

```html
<animateTransform attributeName=''transform''/>
```

**属性:**

*   **从:**动画期间将被修改的属性的初始值。
*   **至:**动画期间将被修改的属性的最终值。
*   **类型:**定义变换的类型，其值随时间变化。
*   **dur:** 动画的持续时间。
*   **重复次数:**动画出现的次数。
*   **重复时间:**重复动画的总持续时间。
*   **属性名称:**将要制作动画的 CSS 属性的名称。

**例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body>
    <svg width="120" height="120">

        <polygon points="60,30 90,90 30,90">
            <animateTransform attributeName="transform"
                attributeType="XML" type="rotate" 
                from="0 60 70" to="360 60 70"
                dur="10s" repeatCount="indefinite" />
        </polygon>
    </svg>
</body>

</html>
```

![](img/a3c23ae70b3ab074118034a9622f0326.png)

## 支持的浏览器:

*   铬
*   边缘
*   火狐浏览器
*   旅行队
*   歌剧