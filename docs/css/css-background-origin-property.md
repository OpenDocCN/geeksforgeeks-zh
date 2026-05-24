# CSS |背景-原点属性

> 原文:[https://www . geesforgeks . org/CSS-background-origin-property/](https://www.geeksforgeeks.org/css-background-origin-property/)

**背景原点**是 CSS 中定义的一个属性，有助于调整网页的背景图像。此属性用于设置背景中图像的原点。默认情况下，此属性将背景图像原点设置为屏幕/网页的左上角。

**语法:**

```html
background-origin: padding-box|border-box|content-box|initial|
inherit;
```

**属性值:**
**初始值:**这是将背景原点设置为左上角填充边缘的初始值/默认值。

*   **语法:**

    ```html
    background-origin: initial;
    ```

*   **Example:**

    ## Hypertext Markup Language

```html
<!DOCTYPE html>
<html>

<head>
    <title>background-origin property</title>
    <style>
        .gfg {
            padding: 40px;
            width: 400px;
            background-image: 
url('https://media.geeksforgeeks.org/wp-content/cdn-uploads/gfg_200X200.png');
            background-repeat: no-repeat;
            background-origin: intial;
            border: 1px double;
            text-align: justify;
        }
    </style>
</head>

<body>
    <div class="gfg">
        <p>
          Prepare for the Recruitment drive of product
          based companies like Microsoft, Amazon, Adobe
          etc with a free online placement preparation
          course. The course focuses on various MCQ's 
          & Coding question likely to be asked in the 
          interviews & make your upcoming placement 
          season efficient and successful. 
        </p>
    </div>
</body>

</html>
```