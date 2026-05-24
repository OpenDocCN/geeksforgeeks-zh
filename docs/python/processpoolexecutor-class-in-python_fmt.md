# Python 中的 ProcessPoolExecutor 类

> 原文: [https://www.geeksforgeeks.org/processpoolexecutor-class-in-python/](https://www.geeksforgeeks.org/processpoolexecutor-class-in-python/)

**先决条件–** [multiprocessing-python-set-1](https://www.geeksforgeeks.org/multiprocessing-python-set-1/)

它允许代码的并行性，Python 语言有两种实现方式，第一种是通过多处理模块，第二种是通过多线程模块。从 Python 3.2 开始，一个名为 `ProcessPoolExecutor` 的新类在 Python 中以并发方式引入。高效管理和创建流程的期货模块。但是等等，如果 python 已经内置了一个多处理模块，那么为什么引入了一个新模块。我先回答这个问题。

*   当进程数量较少时，动态生成新进程不是问题，但如果我们要处理大量进程，管理起来会非常麻烦。此外，创建如此多的进程会导致吞吐量下降，这在计算上是低效的。一种维持吞吐量的方法是预先创建并实例化一个空闲的进程池，并在所有进程耗尽之前重复使用池中的进程。这减少了创建新进程的开销。
*   此外，池会跟踪和管理进程的生命周期，并代表程序员安排它们，从而使代码更简单，错误更少。

## 语法

```python
concurrent.futures.ProcessPoolExecutor(max_workers=None, mp_context=None, initializer=None, initargs=())
```

### 参数

*   `max_workers`: 进程的数量，即池的大小。如果值为 `None`，默认情况下，即使可用核心数超过此值，在 Windows 上也将创建 61 个进程。
*   `mp_context`: 它是一个多进程上下文；如果为空或未指定，将使用默认的多进程上下文。它允许用户控制启动方法。
*   `initializer`: 初始化器接受一个可调用对象，该对象在每个工作进程开始时被调用。
*   `initargs`: 传递给初始化器的一组参数。

## ProcessPoolExecutor 方法

`ProcessPoolExecutor` 类公开了以下异步执行 Process 的方法。下面给出详细的解释。

*   `submit(fn, *args, **kwargs)`: 它运行一个可调用对象或方法，并返回一个 `Future` 对象，该对象表示方法的执行状态。
*   `map(fn, *iterables, timeout=None, chunksize=1)`: 它立即映射方法和可迭代对象，并同时抛出异常。`Future`。如果在超时限制内未能完成，则会发生超时错误。
    *   如果可迭代对象非常大，那么当使用 `ProcessPoolExecutor` 时，大于 1 的块大小可以提高性能。
*   `shutdown(wait=True, *, cancel_futures=False)`:
    *   它向执行器发出信号，在 `Future` 执行完成后释放所有资源。
    *   必须在 `executor.submit()` 和 `executor.map()` 方法之前调用，否则将抛出 `RuntimeError`。
    *   `wait=True` 使此方法不返回，直到所有线程执行完成并释放资源。
    *   `cancel_futures=True` 则执行器将取消所有尚未启动的 `Future` 线程。
*   `cancel()`: 尝试取消调用。如果无法取消调用，则返回 `False`；否则，返回 `True`。
*   `cancelled()`: 如果调用被取消，则返回 `True`。
*   `running()`: 如果进程正在运行且无法取消，则返回 `True`。
*   `done()`: 如果进程已执行完毕，则返回 `True`。
*   `result(timeout=None)`: 返回进程返回的值。如果进程仍在执行，则等待指定的 `timeout`；否则，将引发 `TimeoutError`。如果未指定 `TimeoutError`，则永远等待进程完成。
*   `add_done_callback(fn)`: 附加一个回调函数，该函数在进程执行完成时被调用。

### 例 1

下面的代码演示了 `ProcessPoolExecutor` 的使用，请注意，与多处理模块不同，我们不必使用循环显式调用、使用列表跟踪进程或使用连接等待进程进行同步，或者在进程完成后释放资源。构造函数本身会将所有内容隐藏起来，使代码紧凑且无错误。

### Python 3

```python
from concurrent.futures import ProcessPoolExecutor
from time import sleep

values = [3,4,5,6]
def cube(x):
    print(f'Cube of {x}:{x*x*x}')

if __name__ == '__main__':
    result =[]
    with ProcessPoolExecutor(max_workers=5) as exe:
        exe.submit(cube,2)

# Maps the method 'cube' with a iterable
        result = exe.map(cube,values)

for r in result:
      print(r)
```

**输出:**

```python
Cube of 2:8
Cube of 3:27
Cube of 6:216
Cube of 4:64
Cube of 5:125
```

### 例 2

下面的代码是通过发出一个 HTTP 请求在互联网上获取图像，我使用的是 `requests` 库。代码的第一部分对 API 进行一对一的调用，即下载速度很慢，而代码的第二部分使用多个进程进行并行请求以获取 API。

您可以尝试上面讨论的各种参数，看看它如何调整加速，例如，如果我将进程池设置为 6，而不是 3，加速会更显著。

### Python 3

```python
import requests
import time
import os
import concurrent.futures

img_urls = [
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623210949/download21.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623211125/d11.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623211655/d31.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623212213/d4.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623212607/d5.jpg',
    'https://media.geeksforgeeks.org/wp-content/uploads/20190623235904/d6.jpg',
]

t1 = time.time()
print("Downloading images with single process")
def download_image(img_url):
    img_bytes = requests.get(img_url).content
    print("Downloading..")

for img in img_urls:
    download_image(img)

t2 = time.time()
print(f'Single Process Code Took :{t2-t1} seconds')
print('*'*50)

t1 = time.time()
print("Downloading images with Multiprocess")

def download_image(img_url):
    img_bytes = requests.get(img_url).content
    print(f"[Process ID]:{os.getpid()} Downloading..")

with concurrent.futures.ProcessPoolExecutor(3) as exe:
    exe.map(download_image, img_urls)

t2 = time.time()
print(f'Multiprocess Code Took:{t2-t1} seconds')
```

**输出:**

```python
Downloading images with single process
Downloading..
Downloading..
Downloading..
Downloading..
Downloading..
Downloading..
Single Process Code Took :1.2382981777191162 seconds
**************************************************
Downloading images with Multiprocess
[Process ID]:118741 Downloading..
[Process ID]:118742 Downloading..
[Process ID]:118740 Downloading..
[Process ID]:118741 Downloading..
[Process ID]:118742 Downloading..
[Process ID]:118740 Downloading..
Multiprocess Code Took:0.8398590087890625 seconds
```