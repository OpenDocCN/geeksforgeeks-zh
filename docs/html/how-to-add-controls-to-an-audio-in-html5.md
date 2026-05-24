# 如何在 HTML5 中给音频添加控件？

> 原文:[https://www . geesforgeks . org/如何将控件添加到 html5 音频中/](https://www.geeksforgeeks.org/how-to-add-controls-to-an-audio-in-html5/)

[**HTML <音频>控件**](https://www.geeksforgeeks.org/html-audio-controls-attribute/) 属性用于指定播放音频的控件，这意味着它允许将带有音频控件的 HTML5 音乐播放器直接嵌入网页。

目前 HTML5 最常用的音频格式是 **ogg、mp3** 和 **wav** ，因为浏览器对它们的支持不同，比如火狐不使用插件就不支持 mp3。

**语法:**

```html
<audio controls>
 <source>
</audio>
```

从上面的语法**控件属性**添加音频控件，如播放、暂停和音量， **<源>元素**允许您指定替代音频文件。

音频标签主要支持 5 个属性，如下所示:

1.  **自动播放:**使音频自动开始播放，无需等待整个音频文件下载完成。
2.  **循环:**通过循环可以反复播放音频。
3.  **静音:**使播放器默认静音。
4.  **预载:**这可以设置为以下值。
    *   **auto :** 这意味着文件是否应该在页面加载后立即加载。
    *   **元数据:**这意味着是否只有元数据、曲目标题等。应该是加载的。
    *   **无:**这意味着当页面加载时，浏览器不应该加载文件。
5.  **src:** 这定义了音频标签应该播放的音乐的 url。

**示例 1:** 使用下面代码中的*src* 属性。

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body style="text-align: center"> 
  <h1 style="color: green"> 
    GeeksforGeeks 
  </h1> 

  <h2 style="font-family: Impact"> 
    HTML Audio controls Attribute 
  </h2> 
  <br> 

  <audio id="Test_Audio" controls> 
    <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190531165842/Recording1514.ogg"
      type="audio/ogg"> 

    <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190531165842/Recording1514.mp3"
      type="audio/mpeg"> 

  </audio> 
</body> 

</html>
```

**输出:**

![](img/09967b733dc0ebb560faadca95fd56ab.png)

**示例 2:** 使用*自动播放* **属性自动播放音频。**

## 超文本标记语言

```html
<!DOCTYPE html> 
<html> 

<body style="text-align: center"> 
  <h1 style="color: green"> 
    GeeksforGeeks 
  </h1> 

  <h2 style="font-family: Impact"> 
    HTML Audio controls Attribute 
  </h2> 
  <br> 

  <audio id="Test_Audio" controls autoplay > 
    <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190531165842/Recording1514.ogg"
        type="audio/ogg"> 

    <source src= 
"https://media.geeksforgeeks.org/wp-content/uploads/20190531165842/Recording1514.mp3"
        type="audio/mpeg"> 
  </audio> 
</body> 

</html>
```

**输出:**

![](img/09967b733dc0ebb560faadca95fd56ab.png)