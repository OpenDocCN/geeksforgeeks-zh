# 如何用 Python 打印一个目录内的所有文件？

> 原文：[https://www.geeksforgeeks.org/how-to-print-all-files-within-a-directory-using-python/](https://www.geeksforgeeks.org/how-to-print-all-files-within-a-directory-using-python/)

在本文中，我们将学习“如何使用 Python 打印目录中的所有文件？”。为了完成这项任务，我们使用了 Python 中的 `os` 模块。那么，让我们讨论一些相关的概念。

`os` 模块是最流行的 Python 模块之一，用于自动化操作系统的系统调用和操作。凭借一套丰富的方法和易于使用的 API，`os` 模块是标准包之一，并预装了 Python。

就本文而言，需要 `os` 模块中的以下方法：

1.  `os.startfile()`：此方法打印给定文件的内容。
    > **语法：** `os.startfile(path, operation='open')`
    >
    > **参数：**
    > *   `path` – 包含给定文件路径的字符串
    > *   `operation` – 包含以下一个“命令动词”的字符串
    >     *   `"print"` – 打印与 `path` 相关的文件
    >     *   `"edit"` – 在默认文本编辑器中打开文件进行编辑
    >     *   `"properties"` – 打开给定文件的属性窗口
    >     *   `"find"` – 从 `path` 中提到的目录开始搜索
    >     *   `"open"` – 打开与 `path` 相关的应用程序/文件。如果给定文件不是可执行文件，则打开其关联的应用程序

2.  `os.listdir()`：此方法列出给定目录内的所有文件和目录。关于这个方法的更多细节，包括例子和用例，请参考[这里](https://docs.python.org/3/library/os.html#os.listdir)。
    > **语法：** `os.listdir(path='.')`
    >
    > **参数：**
    > *   `path` – 包含要打印文件目录路径的字符串
    >
    > **返回：** 一个包含相应目录中所有子目录和文件名称的列表。

3.  `os.path.isfile()`：由于我们只能打印给定文件夹的子目录，所以我们将使用这个方法来检查给定的实体是文件还是目录。关于这个方法的更详细的介绍，包括例子和用例，请参考[这里](https://docs.python.org/3/library/os.path.html#os.path.isfile)。
    > **语法：** `os.path.isfile(path)`
    >
    > **参数：**
    > *   `path` – 包含被检查实体路径的字符串
    >
    > **返回：** `True` 如果 `path` 对应一个文件，否则返回 `False`

**注意：** 除了上述模块，您还需要一台功能齐全的打印机连接到您的电脑上！

## 实施

给定脚本的代码行 `time.sleep(5)` 是完全可选的，只是为了避免连续文件中任何不必要的毛刺或操作重叠。更多关于 `time.sleep()` 方法的阅读，请参考[这里](https://docs.python.org/3/library/time.html#time.sleep)。

## 计算机编程语言

```python
# Import libraries
import os
import time

# Insert the directory path in here
path = ''

# Extracting all the contents in the directory corresponding to path
l_files = os.listdir(path)

# Iterating over all the files
for file in l_files:

    # Instantiating the path of the file
    file_path = f'{path}\\{file}'

    # Checking whether the given file is a directory or not
    if os.path.isfile(file_path):
        try:
            # Printing the file pertaining to file_path
            os.startfile(file_path, 'print')
            print(f'Printing {file}')

            # Sleeping the program for 5 seconds so as to account the
            # steady processing of the print operation.
            time.sleep(5)
        except:
            # Catching if any error occurs and alerting the user
            print(f'ALERT: {file} could not be printed! Please check\
            the associated softwares, or the file type.')
    else:
        print(f'ALERT: {file} is not a file, so can not be printed!')

print('Task finished!')
```

**输出：**

演示是在 Windows 10 机器上完成的。环境如下：

*   包含正在打印的文件的目录路径：“本地磁盘(D):/文件”
*   给定目录中的文件：
    *   `Directory` – 一个示例子目录
    *   `File_A.pdf` – 一个样本 `.pdf` 文件
    *   `File_B.txt` – 一个样本 `.txt` 文件
    *   `File_C.docx` – 一个样本 `.docx` 文件

<video class="wp-video-shortcode" id="video-555972-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210209153545/PrintingFilesUsingPythonDemo.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210209153545/PrintingFilesUsingPythonDemo.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210209153545/PrintingFilesUsingPythonDemo.mp4)</video>

**注意：** 由于 `os.startfile()` 只在 Windows 操作系统中可用，因此 macOS 和 Linux 用户在运行文中给出的脚本时可能会遇到一些问题。