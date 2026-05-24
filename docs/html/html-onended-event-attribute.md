# HTML 统一事件属性

> 原文:[https://www.geeksforgeeks.org/html-onended-event-attribute/](https://www.geeksforgeeks.org/html-onended-event-attribute/)

HTML strong 一元属性是一个事件属性，在音频/视频结束时工作。我们可以在这个活动中添加一些自定义消息，如“感谢观看”、“分享”等。

**用法:**此属性用于<音频>和<视频>元素。

**语法:**

```html
<element onended="myScript">
```

*   **属性值:**该属性包含单值脚本，当一个事件属性调用时工作。

**示例:**

```html
<!DOCTYPE html> 
<html> 

<body> 
    <center> 
        <h1 style="color:green">GeeksfroGeeks</h1> 
        <h2>HTML onended Event Attribute</h2> 
        <audio controls onended="gfgFun()"> 
            <source src="beep.mp3" type="audio/mpeg"> 
        </audio> 

        <script> 
            function gfgFun() { 
                alert("Thanks for listning"); 
            } 
        </script> 
    </center> 
</body> 

</html>                    
```

**输出:**

![](img/30fda472a96d0f7c825c42f7dbfd6a04.png)
![](img/5e7a00714f4c2bcf052fa34ccf7e90aa.png)

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   苹果 Safari
*   歌剧