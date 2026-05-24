# 开始使用 PySoundFile

> 原文: [https://www.geeksforgeeks.org/getting-started-with-pysoundfile/](https://www.geeksforgeeks.org/getting-started-with-pysoundfile/)

`PySoundFile` 是一个 Python 模块，用于读取和写入音频文件，将音频文件视为包含音高和所有音高的 `NumPy` 数组。该模块可以读取音频文件，即它从音频中提取 `NumPy` 数组（`.wav` 文件），也能写。

## 安装

运行以下 `pip` 命令：

```py
pip install PySoundFile
```

`PySoundFile` 支持 `libsndfile` 支持的所有格式，例如 WAV、FLAC、OGG 和 mat 文件。

以下是示例中使用的音频文件的链接：[链接](https://drive.google.com/drive/folders/1z419FVosdjv2Tqp2MlJ7n5Q8jRBQaO2W?usp=sharing)

## 读取音频文件

可以使用 `read()` 函数读取音频文件。

### 语法

`read(file, frames=-1, start=0, stop=None, fill_value=None, samplerate=None, channels=None, subtype=None)`

### 参数

*   `file`: 音频文件的路径。
*   `frames`: 此参数用于指定要读取的帧数，默认为 -1，表示要读取整个文件。
*   `start`, `stop`: 指定读取音频文件的开始和结束，默认读取整个文件。
*   `fill_value`: 如果文件中剩余的数据比请求的少，则其余的帧用 `fill_value` 填充。如果未指定 `fill_value`，则返回较小的数组。

### 返回

返回 2 个值：

*   `data`: `numpy` 数组（长度应为 44，100 个元素）。如果返回的是一维 `numpy` 数组，则音频读取为单声道。
*   `samplerate`: 采样率（或“采样率”）定义每秒钟对声音采样的次数。从技术上讲，它是数字录音中使用的样本频率。音频光盘使用的标准采样率是 44.1 kHz，这个文件也是一样的。

### 支持的音频格式

WAV、AIFF、AU、PAF、SVX、NIST、VOC、IRCAM、W64、MAT4、MAT5、PVF、XI、HTK、SDS、AVR、wavex、SD2、FLAC、CAF、WVE、OGG、MPC2K、RF64。

### 示例

我们将读取以下文件：

<audio class="wp-audio-shortcode" id="audio-500215-1" preload="none" style="width:100%" controls=""><source type="audio/wav" src="https://media.geeksforgeeks.org/wp-content/uploads/20201019155155/noice.wav?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201019155155/noice.wav](https://media.geeksforgeeks.org/wp-content/uploads/20201019155155/noice.wav)</audio>

```py
# import the module
import soundfile as sf

# read the file
data, samplerate = sf.read('noice.wav')

# display the data
print(data)
print("---------------------")
print("Sample Rate is ", samplerate)
print("---------------------")
print("Done")
```

**输出:**

![](img/8c1bab8a50eb6490443b83166897ed8f.png)

## 写文件

我们可以使用 `write()` 函数写文件。

### 语法

`write(file, data, samplerate, subtype=None, endian=None, format=None, closefd=True)`

### 参数

*   `file`: 输出文件的路径。
*   `data`: 待写数据。
*   `samplerate`: 音频数据采样率。

### 返回

无。

要写音频文件，我们需要 `NumPy` 数组（即 `data`），因为采样率有标准值，它以 `wb` 模式打开文件，即如果存在相同的名称，那么程序将重写它。

### 示例

我们将读取以下文件：

<audio class="wp-audio-shortcode" id="audio-500215-2" preload="none" style="width:100%" controls=""><source type="audio/wav" src="https://media.geeksforgeeks.org/wp-content/uploads/20201019155510/Sample.wav?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20201019155510/Sample.wav](https://media.geeksforgeeks.org/wp-content/uploads/20201019155510/Sample.wav)</audio>

```py
# importing the module
import soundfile as sf

# reading the file
data, samplerate = sf.read('Sample.wav')

# writing the file
sf.write('writing_file_output.wav', data, samplerate)

# You may compare both audio, link is given in the output
```

**输出:** 这是输出文件：

<audio class="wp-audio-shortcode" id="audio-500215-3" preload="none" style="width:100%" controls=""><source type="audio/wav" src="https://media.geeksforgeeks.org/wp-content/uploads/20201019155432/writing_file_output.wav?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20201019155432/writing_file_output.wav](https://media.geeksforgeeks.org/wp-content/uploads/20201019155432/writing_file_output.wav)</audio>