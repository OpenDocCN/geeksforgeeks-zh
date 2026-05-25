# Python–用 OpenCV 写视频

> 原文: [https://www.geeksforgeeks.org/python-writing-to-video-with-opencv/](https://www.geeksforgeeks.org/python-writing-to-video-with-opencv/)

在本文中，我们将讨论如何使用 Python 中的 OpenCV 编写视频。

## 方法

*   将所需的库导入工作空间。
*   阅读你必须写的视频。

### 语法

```py
cap = cv2.VideoCapture("path")
```

*   使用 `cv2.VideoWriter_fourcc()` 方法创建输出文件。

### 语法

```py
output = cv2.VideoWriter("path", cv2.VideoWriter_fourcc(*'MPEG'), 30, (1080, 1920))
```

*   然后通过添加形状来编辑视频的帧（对于这里给出的例子，同样的方法可以应用于任何其他技术。）。

### 语法

```py
cv2.rectangle(frame, (100, 100), (500, 500), (0, 255, 0), 3)
```

*   然后写视频。

### 语法

```py
output.write(frame)
```

### 示例：写入视频的程序

**使用的视频:**

[https://media.geeksforgeeks.org/wp-content/uploads/20210926125350/input.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210926125350/input.mp4)

## 示例代码

```py
import cv2

def main():
    # reading the input
    cap = cv2.VideoCapture("input.mp4")

    output = cv2.VideoWriter(
        "output.avi", cv2.VideoWriter_fourcc(*'MPEG'), 30, (1080, 1920))

    while(True):
        ret, frame = cap.read()
        if(ret):
            # adding rectangle on each frame
            cv2.rectangle(frame, (100, 100), (500, 500), (0, 255, 0), 3)

            # writing the new frame in output
            output.write(frame)
            cv2.imshow("output", frame)
            if cv2.waitKey(1) & 0xFF == ord('s'):
                break

    cv2.destroyAllWindows()
    output.release()
    cap.release()

if __name__ == "__main__":
    main()
```

**输出:**

[https://media.geeksforgeeks.org/wp-content/uploads/20210926153928/output_final.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210926153928/output_final.mp4)