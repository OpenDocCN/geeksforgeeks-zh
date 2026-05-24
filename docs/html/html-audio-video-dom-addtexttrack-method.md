# HTML 音视频 DOM addTextTrack()方法

> 原文:[https://www . geesforgeks . org/html-audio-video-DOM-addtexttrack-method/](https://www.geeksforgeeks.org/html-audio-video-dom-addtexttrack-method/)

**HTML 视频 DOM 添加文本轨迹()方法**用于创建或返回视频元素的新文本轨迹。新的文本轨道被添加到视频元素的所有文本轨道列表中。

**语法:**

```html
audio/video.addTextTrack(kind, label, language)
```

**参数值:**

*   **种类:**指定文本轨道的种类
    **Possible values are:**

*   “字幕”*   "标题"*   “描述”*   “章节”*   "元数据"*   **标签:**它包含一个指定文本轨道标签的字符串值*   **language:** It contains a two-letter language code which specifying a language of the Texttrack.

    **返回值:**返回一个表示视频元素新文本轨迹的文本轨迹对象。

    **示例:**

    ```html
    <!DOCTYPE html>
    <html>

    <head>
        <title>
            HTML DOM addTextTrack() Method
        </title>
    </head>

    <body>
        <center>
            <h1 style="color:green;">  
                    GeeksForGeeks  
                </h1>

            <h2>
              HTML DOM Video addTextTrack() Method
          </h2>

            <video id="gfg"
                   width="320" 
                   height="240" 
                   controls>
                <source src=
    "https://media.geeksforgeeks.org/wp-content/uploads/project.mp4"
                        type="video/mp4">
            </video>

            <br>

            <button type="button" 
                    onclick="myGeeks()">
                New Text Track
            </button>

            <script>
                var GFG = document.getElementById("gfg");

                function myGeeks() {
                    var sudo = GFG.addTextTrack("caption");
                    sudo.addCue(new TextTrackCue(
                      "Test text", 01.000, 04.000, "", "", "", true));
                }
            </script>
          </center>
    </body>

    </html>
    ```

    **输出:**
    ![](img/77123c1acbbe5d495a76fb3c204b4da1.png)