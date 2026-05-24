# Python 中的 Psutil 模块

> 原文:[https://www.geeksforgeeks.org/psutil-module-in-python/](https://www.geeksforgeeks.org/psutil-module-in-python/)

`Psutil` 是一个 Python 跨平台库，用于访问系统细节和流程实用程序。它用于跟踪系统中各种资源的利用情况。可以监控 CPU、内存、磁盘、网络、传感器等资源的使用情况。因此，该库用于系统监控、分析、限制进程资源和管理正在运行的进程。Python、2.7 和 3.4+版本支持它。

### Linux Ubuntu/Debian 中的安装步骤

```py
sudo pip install psutil
```

## 系统功能

### 中央处理器

**1) `psutil.cpu_times()`** – 该函数以命名元组的形式给出系统 CPU 时间。

**参数:**

*   `user` – 正常进程在用户模式下执行所花费的时间
*   `system` – 进程在内核模式下执行所花费的时间
*   `idle` – 系统空闲的时间
*   `nice` – 优先进程在用户模式下执行所花费的时间
*   `iowait` – 等待输入/输出完成的时间。这不计入空闲时间计数器。
*   `irq` – 服务硬件中断所花费的时间
*   `softirq` – 服务软件中断所花费的时间
*   `steal` – 在虚拟化环境中运行的其他操作系统花费的时间
*   `guest` – 在 Linux 内核的控制下运行来宾操作系统的虚拟 CPU 所花费的时间

**示例:**

```py
import psutil

print(psutil.cpu_times())
```

**输出**

> scputimes(user=5461.14, nice=2.44, system=1326.65, idle=45502.33, iowait=506.24, irq=0.0, softirq=5.46, steal=0.0, guest=0.0, guest_nice=0.0)

**2) `psutil.cpu_percent(interval)`** – 此函数计算当前系统范围内的 CPU 利用率百分比。建议将时间间隔(秒)作为计算平均 CPU 使用率的函数的参数，忽略时间间隔参数可能会导致使用率值出现较大变化。

**示例:**

```py
import psutil

print(psutil.cpu_percent(1))
```

**输出**

```py
5.0
```

**3) `psutil.cpu_count(logical=True)`** – 此功能显示系统中的逻辑 cpu 数量。逻辑内核的计算方法是物理内核的数量乘以每个内核上可以运行的线程数量。在没有逻辑内核的情况下，它只计算物理内核的数量。

**示例:**

```py
import psutil

print("Number of cores in system", psutil.cpu_count())
print("\nNumber of physical cores in system", psutil.cpu_count(logical=False))
```

**输出:**

```py
Number of cores in system 4
Number of physical cores in system 2
```

**4) `psutil.cpu_stats()`** – 该函数将 CPU 统计数据作为命名元组给出。统计数据包括:

*   `ctx_switches` – 自引导以来上下文切换的次数。
*   `interrupts` – 启动后的中断次数。
*   `soft_interrupts` – 自引导以来软件中断的次数。
*   `syscalls` – 自引导以来的系统调用次数。在 Ubuntu 中总是设置为 0。

**示例:**

```py
import psutil

print("CPU Statistics", psutil.cpu_stats())
```

> scpustats(ctx_switches=37382771, interrupts=13744347, soft_interrupts=6769413, syscalls=0)

**5) `psutil.cpu_freq()`** – 该函数将 CPU 频率作为一个元组给出，该元组包括以 Mhz 表示的当前、最小和最大频率。Ubuntu 上的当前频率报告实时值。而在所有其他平台上，它代表名义上的“固定”值。

**示例:**

```py
import psutil

print(psutil.cpu_freq())
```

**输出:**

> scpufreq(current=931.42925, min=400.0, max=2000.0)

**6) `psutil.getloadavg()`** – 该函数以元组的形式给出最近 1 分钟、5 分钟和 15 分钟的平均系统负载。负载表示处于可运行状态的进程，使用中央处理器或等待使用中央处理器(例如，等待磁盘输入/输出)。

**示例:**

```py
import psutil

print(psutil.getloadavg())
```

**输出:**

```py
(0.22, 0.33, 0.35)
```

### 记忆

**1) `psutil.virtual_memory()`** – 该函数以字节为单位给出系统内存使用情况。已用和可用的总和可能等于也可能不等于总数。为了获得空闲物理内存的详细信息，使用了这个函数。

**参数:**

*   `total` – 不包括交换的总物理内存。
*   `available` – 无需系统交换即可立即分配给进程的内存。
*   `used` – 已用内存。
*   `free` – 内存未在使用，并且随时可用
*   `active` – 当前正在使用或最近使用的内存。
*   `inactive` – 标记为未使用的内存。
*   `buffers` – 缓存文件系统元数据等数据。
*   `cached` – 缓存的数据
*   `shared` – 可由多个进程访问的内存。

**示例:**

```py
import psutil

print(psutil.virtual_memory())
```

**输出:**

> svmem(total=4028772352, available=1061466112, percent=73.7, used=2401546240, free=412352512, active=2176798720, inactive=1196470272, buffers=70774784, cached=1144098816, shared=313872384, slab=31382384)

**2) `psutil.swap_memory()`** – 该函数以元组的形式提供交换内存统计的详细信息。

**参数:**

*   `total` – 总交换内存(字节)
*   `used` – 已用交换内存(字节)
*   `free` – 以字节为单位的空闲交换内存
*   `percent` – 使用百分比，计算方式为`(total - free) / total * 100`
*   `sin` – 系统从磁盘换入的字节数
*   `sout` – 系统从磁盘换出的字节数

**示例:**

```py
import psutil

print(psutil.swap_memory())
```

**输出:**

> sswap(total=2097147904L, used=886620160L, free=1210527744L, percent=42.3, sin=1050411008, sout=1906720768)

### 磁盘

**1) `psutil.disk_partitions()`** – 该功能以元组列表的形式提供所有已挂载磁盘分区的详细信息，包括设备、挂载点和文件系统类型。

**示例:**

```py
import psutil

print(psutil.disk_partitions())
```

**输出:**

> [sdiskpart(device='/dev/sda1', mountpoint='/', fstype='ext4', opts='rw,relatime,errors=remount-ro,data=ordered')]

**2) `psutil.disk_usage(path)`** – 该函数给出给定路径的元组形式的磁盘使用统计信息。总空间、已用空间和可用空间以及使用百分比都以字节表示。

**示例:**

```py
import psutil

print(psutil.disk_usage('/'))
```

**输出:**

> sdiskusage(total=787310764032, used=26450710528, free=720843354112, percent=3.5)

### 网络

**1) `psutil.net_io_counters()`** – 该函数以元组的形式给出网络输入输出统计的详细信息。

**参数:**

*   `bytes_sent` – 发送的字节数
*   `bytes_recv` – 接收的字节数
*   `packets_sent` – 发送的数据包数量
*   `packets_recv` – 收到的数据包数量
*   `errin` – 接收时的错误总数
*   `errout` – 发送时的错误总数
*   `dropin` – 丢弃的传入数据包总数
*   `dropout` – 丢弃的传出数据包总数

**示例:**

```py
import psutil

print(psutil.net_io_counters())
```

**输出:**

> snetio(bytes_sent=14508483, bytes_recv=62749361, packets_sent=84311, packets_recv=94888, errin=0, errout=0, dropin=0, dropout=0)

**2) `psutil.net_connections()`** – 该函数将系统的套接字连接列表作为命名元组给出。

**参数:**

*   `fd` – 套接字文件描述符。
*   `family` – 套接字系列，可以是 `AF_INET`、`AF_INET6` 或 `AF_UNIX`。
*   `type` – 套接字类型，可以是 `SOCK_STREAM`、`SOCK_DGRAM` 或 `SOCK_SEQPACKET`。
*   `laddr` – 本地地址(ip, 端口)命名元组
*   `raddr` – 作为(ip, 端口)命名元组的远程地址
*   `status` – 表示 TCP 连接的状态。
*   `pid` – 打开套接字的进程的 PID，如果可检索，则为无。

**示例:**

```py
import psutil

print(psutil.net_connections())
```

**输出:**

> [sconn(fd=118, family=2, type=1, laddr=addr(ip='192.168.12.184', port=59666), raddr=addr(ip='172.217.166.42', port=443), status='ESTABLISHED', pid=2428),
> sconn(fd=-1, family=2, type=2, laddr=addr(ip='0.0.0.0', port=0), raddr=None, status='NONE', pid=0)]

**3) `psutil.net_if_addrs()`** – 此功能用于获取系统上安装的每个网络接口卡的地址。它是一个字典，其关键字是网络接口卡名称，值是分配给它的每个地址的命名元组列表。每个元组包括:

*   `family` – 套接字系列，`AF_INET` 或 `AF_INET6`
*   `address` – 主网卡地址
*   `netmask` – 网络掩码地址
*   `broadcast` – 广播地址。
*   `ptp` – “点对点”它是点对点接口上的目的地址。

**示例:**

```py
import psutil

print(psutil.net_if_addrs())
```

**输出:**

> { 'wlo1': [snicaddr(family=2, address='192.168.12.184', netmask='255.255.255.0', broadcast='192.168.12.255', ptp=None), snicaddr(family=10, address='fe80::664f:767c:91f0:71c0%wlo1', netmask='ffff:ffff:ffff:ffff:ffff:ffff:ffff:ffff', broadcast=None, ptp=None)] }

### 传感器

**1) `psutil.sensors_temperatures()`** – 此功能以摄氏度为单位返回系统的硬件温度。每个条目都是一个命名元组，代表某个硬件温度传感器。

**示例:**

```py
import psutil

print(psutil.sensors_temperatures())
```

**输出:**

> {'acpitz': [shwtemp(label='', current=27.8, high=119.0, critical=119.0), shwtemp(label='', current=29.8, high=119.0, critical=119.0), shwtemp(label='', current=10.0, high=None, critical=None)], 'coretemp': [shwtemp(label='Physical id 0', current=42.0, high=100.0, critical=100.0), shwtemp(label='Core 0', current=35.0, high=100.0, critical=100.0)]}

**2) `psutil.sensors_fans()`** – 此功能给出硬件风扇速度的详细信息，以 RPM(每分钟转数)表示。如果操作系统不支持传感器，将返回一个空字典。

**示例:**

```py
import psutil

print(psutil.sensors_fans())
```

**输出:**

```py
{'asus': [sfan(label='cpu_fan', current=3000)]}
```

**3) `psutil.sensors_battery()`** – 此功能以命名元组的形式给出电池状态信息。

**参数:**

*   `percent` – 剩余的电池电量百分比。
*   `secsleft` – 电池完全放电前的大约时间(秒)。
*   `power_plugged` – 如果连接了交流电源线，则为 `True` 如果没有连接，则为 `False`。

**示例:**

```py
import psutil

print(psutil.sensors_battery())
```

**输出:**

> sbattery(percent=98.98572501878287, secsleft=22913, power_plugged=False)

### 其他系统信息

**1) `psutil.boot_time()`** – 此函数返回系统启动时间，以自纪元以来的秒数表示。

**示例:**

```py
import psutil, datetime

print(psutil.boot_time())
```

**输出:**

```py
1582860765.0
```

**2) `psutil.users()`** – 该函数给出了以命名元组形式连接到系统的用户列表。

**参数:**

*   `name` – 这是用户的系统名称。
*   `terminal` – 用户的 tty。
*   `host` – 用户的主机名。
*   `started` – 自纪元以来以秒为单位表示的浮点数的创建时间。
*   `pid` – 登录过程的 PID。

**示例:**

```py
import psutil

print(psutil.users())
```

**输出:**

> [suser(name='admin1', terminal='tty7', host='localhost', started=1582860800.0, pid=1747)]