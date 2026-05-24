# 影片–获取视频文件剪辑的开始时间

> 原文: [https://www.geeksforgeeks.org/moviepy-getting-start-time-of-video-file-clip/](https://www.geeksforgeeks.org/moviepy-getting-start-time-of-video-file-clip/)

在本文中，我们将了解如何在 MoviePy 中获取视频文件剪辑的开始时间。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。当剪辑包含在合成中时，开始时间是剪辑开始播放的合成时间(以秒为单位)。

> 为了做到这一点，我们将使用视频文件剪辑对象的`start`属性
> **语法:** `clip.start`
> **论证:** 不需要论证
> **返回:** 返回整数

下面是实现

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# getting start time of the clip
value = clip.start

# printing start time
print("Start Time : ", end =" ")
print(value)

# showing  clip
clip.ipython_display(width = 360)
```

**输出:**

```py
Start Time :  0
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

[https://media.geeksforgeeks.org/wp-content/uploads/20200825235530/1st2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200825235530/1st2.mp4)

## 另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# getting start time of the clip
value = clip.start

# printing start time
print("Start Time : ", end =" ")
print(value)

# showing  clip
clip.ipython_display(width = 360)
```

**输出:**

```py
Start Time :  0
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

[https://media.geeksforgeeks.org/wp-content/uploads/20200825235546/2nd2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200825235546/2nd2.mp4)