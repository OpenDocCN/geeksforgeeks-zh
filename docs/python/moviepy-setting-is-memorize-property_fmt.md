# 移动-设置为记忆属性

> 原文：[https://www.geeksforgeeks.org/moviepy-setting-is-memorize-property/](https://www.geeksforgeeks.org/moviepy-setting-is-memorize-property/)

在本文中，我们将看到如何在 MoviePy 中设置视频文件剪辑的 `memoize` 属性。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。一个视频是多个帧的组合，因此每次都有一个特定的帧。`memoize` 属性告诉剪辑是否应该保留在内存中读取的最后一帧。

## 语法

为此，我们将对视频文件剪辑对象使用 `set_memoize` 方法。

**语法：** `clip.set_memoize(True)`

**参数：** 它以布尔值为参数。

**返回：** 返回视频文件剪辑对象。

## 实现

下面是实现。

### 示例 1

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# setting memorize property
new_clip = clip.set_memoize(True)

# displaying new clip
new_clip.ipython_display(width = 420)
```

**输出：**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

[视频链接](https://media.geeksforgeeks.org/wp-content/uploads/20200827002306/1st9.mp4)

### 示例 2

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# setting memorize property
new_clip = clip.set_memoize(True)

# displaying new clip
new_clip.ipython_display(width = 420)
```

**输出：**

```py
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

[视频链接](https://media.geeksforgeeks.org/wp-content/uploads/20200827002455/2nd8.mp4)