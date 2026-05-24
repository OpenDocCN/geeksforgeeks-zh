# HTML | video height Attribute

> 原文：[https://www.geeksforgeeks.org/html-video-height-attribute/](https://www.geeksforgeeks.org/html-video-height-attribute/)

The **HTML <video> height attribute** is used to specify the height of the video player in terms of pixels.

**Syntax:**

```html
<video height="pixels">
```

**Attribute Values:** It contains single value **pixels** which specifies the height of the video player in terms of pixels.

Below example illustrates the use of height attribute in <video> element:

**Example:**

```html
<!DOCTYPE html> 
<html> 

<head> 
    <title> 
        HTML video height Attribute 
    </title> 
</head> 

<body style="text-align: center"> 

    <h1 style="color: green"> 
        GeeksforGeeks 
    </h1> 

    <h2> 
        HTML video height Attribute
    </h2> 
    <br> 

    <video id="Test_Video" width="360" height="200"
            controls> 
        <source src="sample_vid.mp4" type="video/mp4"> 
        <source src="sample_vid.ogg" type="video/ogg"> 
    </video> 
</body> 

</html>                    
```

**Output:**
![](img/7497e28159bd7c98bb3a29d6ea0fc03d.png)

**Supported Browsers:** The browser supported by HTML video height attribute are listed below:

*   Google Chrome
*   Internet Explorer
*   Firefox
*   Safari
*   Opera