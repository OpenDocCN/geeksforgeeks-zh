# P5.js | `shininess()`功能

> 原文: [https://www.geeksforgeeks.org/p5-js-shininess-function/](https://www.geeksforgeeks.org/p5-js-shininess-function/)

p5.js 中的 `shininess()` 功能用于指定形状表面的光泽度。与 `specularMaterial()` 功能结合使用，设置材质属性。

## 语法:

```
shininess( shine )
```

## 参数:

该函数接受一个参数，如下所述。

*   `shine`: 是一个数字，指定一个元素的闪耀程度。默认值为 1。

下面的例子说明了 p5.js 中的 `shininess()` 功能:

## 示例:

```
let newFont;

function preload() {
  newFont = loadFont('fonts/Montserrat.otf');
}

function setup() {
  createCanvas(500, 300, WEBGL);
  shineInput = createSlider(0, 100, 50, 1);
  shineInput.position(20, 40);
  textFont(newFont);
  textSize(20);
}

function draw() {
  background('green');
  text("Move the slider to change the shininess value", -235, -125);
  noStroke();
  ambientLight(60, 60, 60);
  pointLight(255, 255, 255, width / 2, height / 2, 75);
  specularMaterial(250);
  shininess(shineInput.value());

  sphere(75);
}
```

## 输出:

![shininess-slider](img/e1d70aff02fd608fce2ea29f442e5f63.png)

## 在线编辑:

[https://editor.p5js.org/](https://editor.p5js.org/)

## 环境设置:

## 参考:

[https://p5js.org/reference/#/p5/shininess](https://p5js.org/reference/#/p5/shininess)