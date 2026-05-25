# Node.js os.constants

> 原文: [https://www.geeksforgeeks.org/node-js-os-constants/](https://www.geeksforgeeks.org/node-js-os-constants/)

`os.constants` 是 `os` 模块内置的应用编程接口，用于获取操作系统指定的错误代码常量、信号常量、优先级常量、dlopen 常量等。

**语法:**

```js
os.constants
```

**返回值:** 返回包含操作系统指定常量的对象。例如：错误代码、信号常数、优先级常数、数据打开常数等。

信号常数可以通过使用 `os.constants.signal` 来访问，优先级常数可以通过使用 `os.constants.priority` 来访问，下面列出了一些常数：

## 信号常数

| 常数 | 描述 |
| --- | --- |
| SIGHUP | 它被发送来指定父进程何时退出或控制终端何时关闭。 |
| SIGINT | 它被发送来指定用户何时中断进程（比如 `(Ctrl+C)`）。 |
| SIGQUIT | 它被发送来指定用户希望终止进程并执行核心转储。 |
| SIGILL | 它被发送到一个进程，通知它试图执行一个格式错误、未知、非法或特权指令。 |
| SIGTRAP | 发生异常时，它被发送到进程。 |
| SIGABRT | 它被发送到一个进程以请求中止。 |
| SIGBUS | 它是 `SIGABRT` 的同义词。 |
| SIGFPE | 它被发送到一个进程，通知非法的算术运算。 |
| SIGKILL | 它被发送到一个进程以立即终止。 |
| SIGUSR1 | 它被发送到一个进程，以识别用户定义的条件。 |
| SIGSEGV | 它被发送到一个进程以通知分段故障。 |
| SIGPIPE | 当进程尝试写入断开的管道时，它会被发送到该进程。 |
| SIGALRM | 它被发送到一个进程，等待系统定时器到时。 |
| SIGTERM | 它被发送到一个进程以请求终止。 |
| SIGCHLD | 它在子进程终止后被发送到一个进程。 |
| SIGSTKFLT | 它被发送到一个进程，以指定协处理器上的堆栈故障。 |
| SIGCONT | 它被发送来告诉操作系统继续暂停的进程。 |
| SIGSTOP | 它被发送来指示操作系统停止一个进程。 |
| SIGTSTP | 它被发送到一个进程，请求它停止。 |
| SIGBREAK | 它被发送来指定用户希望中断一个进程。 |
| SIGTTIN | 当进程在后台从 TTY 读取数据时，会发送该消息。 |
| SIGTTOU | 当进程在后台写入 TTY 时，会发送该消息。 |
| SIGURG | 它被发送到一个进程，指示套接字有紧急数据要读取。 |
| SIGXCPU | 当进程超过其 CPU 使用限制时发送。 |
| SIGXFSZ | 当进程增长的文件大于允许的最大值时发送。 |
| SIGVTALRM | 它被发送到一个进程，用于经过的虚拟计时器事件。 |
| SIGPROF | 它在系统定时器超时后被发送到一个进程。 |
| SIGWINCH | 在控制终端改变其大小后，它被发送到一个进程。 |
| SIGIO | 它被发送到一个进程，表示输入/输出可用。 |
| SIGPOLL | 它是 `SIGIO` 的同义词。 |
| SIGLOST | 它被发送到一个进程，表示文件锁已经丢失。 |
| SIGPWR | 它被发送到进程以通知电源故障。 |
| SIGINFO | 它是 `SIGPWR` 的同义词。 |
| SIGSYS | 它被发送到一个进程，通知错误的参数。 |
| SIGUNUSED | 它是 `SIGSYS` 的同义词。 |

## 误差常数

### 1. POSIX 误差常数

| 常数 | 描述 |
| --- | --- |
| E2BIG | 它是指定一个比预期更长的参数列表。 |
| EACCES | 是为操作指定的权限不足。 |
| EADDRINUSE | 它是指定一个已经使用的网络地址。 |
| EADDRNOTAVAIL | 它用于指定当前不可用的网络地址。 |
| EAFNOSUPPORT | 它是指定不支持的网络地址族。 |
| EAGAIN | 这是为了指定没有可用的数据，并在稍后重试该操作。 |
| EALREADY | 它用于指定套接字有一个正在进行的挂起连接。 |
| EBADF | 它是指定一个无效的文件描述符。 |
| EBADMSG | 它是指定一个无效的数据消息。 |
| EBUSY | 它用于指定设备或资源正忙。 |
| ECANCELED | 它用于指定操作已被取消。 |
| ECHILD | 它是指定不要有任何子进程。 |
| ECONNABORTED | 它用于指定中止的网络连接。 |
| ECONNREFUSED | 它是指定被拒绝的网络连接。 |
| ECONNRESET | 它是指定重置网络连接。 |
| EDEADLK | 它是指定一个避免的资源死锁。 |
| EDESTADDRREQ | 它指定需要目的地地址。 |
| EDOM | 它指定一个参数超出了函数的范围。 |
| EDQUOT | 它用于指定磁盘配额已被超过。 |
| EEXIST | 它是指定文件已经存在。 |
| EFAULT | 它是指定一个无效的指针地址。 |
| EFBIG | 是指定文件太大。 |
| EHOSTUNREACH | 它指定主机不可访问。 |
| EIDRM | 它指定标识符已被删除。 |
| EILSEQ | 它是指定一个非法的字节序列。 |
| EINPROGRESS | 它指定一个操作已经在进行中。 |
| EINTR | 它指定函数调用被中断。 |
| EINVAL | 它指定提供了无效的参数。 |
| EIO | 它用于指定一个未指定的输入/输出错误。 |
| EISCONN | 它是指定套接字已连接。 |
| EISDIR | 它是指定路径是一个目录。 |
| ELOOP | 它是在一个路径中指定太多级别的符号链接。 |
| EMFILE | 是指定打开的文件太多。 |
| EMLINK | 它是指定有太多的硬链接到一个文件。 |
| EMSGSIZE | 它指定提供的消息太长。 |
| EMULTIHOP | 它指定尝试了多跳。 |
| ENAMETOOLONG | 是指定文件名太长。 |
| ENETDOWN | 它用于指定网络已关闭。 |
| ENETRESET | 它指定网络已经中止连接。 |
| ENETUNREACH | 它指定网络不可达。 |
| ENFILE | 是指定系统中打开的文件太多。 |
| ENOBUFS | 它指定没有可用的缓冲空间。 |
| ENODATA | 它指定在流头读取队列中没有可用的消息。 |
| ENODEV | 它是指定没有这样的设备。 |
| ENOENT | 它是指定没有这样的文件或目录。 |
| ENOEXEC | 它是指定一个 exec 格式错误。 |
| ENOLCK | 它指定没有可用的锁。 |
| ENOLINK | 它是指定一个链接已被切断。 |
| ENOMEM | 是指定空间不够。 |
| ENOMSG | 它指定没有所需类型的消息。 |
| ENOPROTOOPT | 它指定给定的协议不可用。 |
| ENOSPC | 它指定设备上没有可用空间。 |
| ENOSR | 它指定没有可用的流资源。 |
| ENOSTR | 它指定给定的资源不是流。 |
| ENOSYS | 它是指定一个功能还没有实现。 |
| ENOTCONN | 它是指定套接字未连接。 |
| ENOTDIR | 它是指定路径不是目录。 |
| ENOTEMPTY | 它是指定目录不为空。 |
| ENOTSOCK | 它指定给定的项目不是套接字。 |
| ENOTSUP | 它指定不支持给定的操作。 |
| ENOTTY | 它是指定一个不适当的输入输出控制操作。 |
| ENXIO | 它是指定没有这样的设备或地址。 |
| EOPNOTSUPP | 它用于指定套接字上不支持的操作。虽然 `ENOTSUP` 和 `EOPNOTSUPP` 在 Linux 上具有相同的值，但是根据 POSIX.1，这些错误值应该是不同的。 |
| EOVERFLOW | 它指定值太大，无法存储在给定的数据类型中。 |
| EPERM | 它指定不允许操作。 |
| EPIPE | 它是指定一个破裂的管道。 |
| EPROTO | 它是指定一个协议错误。 |
| EPROTONOSUPPORT | 它是指定一个不支持的协议。 |
| EPROTOTYPE | 它是为套接字指定错误的协议类型。 |
| ERANGE | 是指定结果太大。 |
| EROFS | 它指定文件系统是只读的。 |
| ESPIPE | 它是指定一个无效的查找操作。 |
| ESRCH | 是指明没有这样的过程。 |
| ESTALE | 它是指定文件句柄是陈旧的。 |
| ETIME | 它是指定一个过期的计时器。 |
| ETIMEDOUT | 是指定连接超时的时间。 |
| ETXTBSY | 它用于指定文本文件正忙。 |
| EWOULDBLOCK | 它指定操作将被阻止。 |
| EXDEV | 就是指定一个不恰当的链接。 |

### 2. Windows 特定错误

| 常数代码 | 常数描述 |
| --- | --- |
| WSAEINTR | 它是指定一个中断的函数调用。 |
| WSAEBADF | 它是指定一个无效的文件句柄。 |
| WSAEACCES | 是指定权限不足，无法完成操作。 |
| WSAEFAULT | 它是指定一个无效的指针地址。 |
| WSAEINVAL | 它指定传递了无效的参数。 |
| WSAEMFILE | 是指定打开的文件太多。 |
| WSAEWOULDBLOCK | 它指定资源暂时不可用。 |
| WSAEINPROGRESS | 它用于指定当前正在进行的操作。 |
| WSAEALREADY | 它指定一个操作已经在进行中。 |
| WSAENOTSOCK | 它指定资源不是套接字。 |
| WSAEDESTADDRREQ | 它指定需要目的地地址。 |
| WSAEMSGSIZE | 它是指定消息太长。 |
| WSAEPROTOTYPE | 它是为套接字指定错误的协议类型。 |
| WSAENOPROTOOPT | 它是指定一个错误的协议选项。 |
| WSAEPROTONOSUPPORT | 它指定不支持该协议。 |
| WSAESOCKTNOSUPPORT | 它是指定不支持套接字类型。 |
| WSAEOPNOTSUPP | 是指定不支持该操作。 |
| WSAEPFNOSUPPORT | 它指定不支持协议系列。 |
| WSAEAFNOSUPPORT | 是指定不支持地址族。 |
| WSAEADDRINUSE | 它指定网络地址已经在使用中。 |
| WSAEADDRNOTAVAIL | 它指定网络地址不可用。 |
| WSAENETDOWN | 它用于指定网络已关闭。 |
| WSAENETUNREACH | 它指定网络不可达。 |
| WSAENETRESET | 它指定网络连接已被重置。 |
| WSAECONNABORTED | 它指定连接已被中止。 |
| WSAECONNRESET | 它指定对等方已重置连接。 |
| WSAENOBUFS | 它指定没有可用的缓冲空间。 |
| WSAEISCONN | 它指定套接字已经连接。 |
| WSAENOTCONN | 它是指定套接字未连接。 |
| WSAESHUTDOWN | 它是指定套接字关闭后不能发送数据。 |
| WSAETOOMANYREFS | 是指定引用太多。 |
| WSAETIMEDOUT | 它指定连接已经超时。 |
| WSAECONNREFUSED | 它指定连接已被拒绝。 |
| WSAELOOP | 它是指定一个名字不能被翻译。 |
| WSAENAMETOOLONG | 它是指定一个名称太长。 |
| WSAEHOSTDOWN | 它用于指定网络主机已关闭。 |
| WSAEHOSTUNREACH | 它指定没有到网络主机的路由。 |
| WSAENOTEMPTY | 它是指定目录不为空。 |
| WSAEPROCLIM | 是指定流程太多。 |
| WSAEUSERS | 它是指定已经超过用户配额。 |
| WSAEDQUOT | 它用于指定磁盘配额已被超过。 |
| WSAESTALE | 它是指定一个陈旧的文件句柄引用。 |
| WSAEREMOTE | 它是指定项目是远程的。 |
| WSASYSNOTREADY | 它指定网络子系统未准备好。 |
| WSAVERNOTSUPPORTED | 是指定 `winsock.dll` 版本超出范围。 |
| WSANOTINITIALISED | 它用于指定尚未执行成功的 `WSAStartup`。 |
| WSAEDISCON | 它用于指定正常关机正在进行中。 |
| WSAENOMORE | 是指定不再有结果。 |
| WSAECANCELLED | 它用于指定操作已被取消。 |
| WSAEINVALIDPROCTABLE | 它是指定过程调用表无效。 |
| WSAEINVALIDPROVIDER | 它是指定一个无效的服务提供者。 |
| WSAEPROVIDERFAILEDINIT | 它是指定服务提供者初始化失败。 |
| WSASYSCALLFAILURE | 它用于指定系统调用失败。 |
| WSASERVICE_NOT_FOUND | 它用于指定未找到服务。 |
| WSATYPE_NOT_FOUND | 它用于指定找不到类类型。 |
| WSA_E_NO_MORE | 是指定不再有结果。 |
| WSA_E_CANCELLED | 它用于指定呼叫已被取消。 |
| WSAEREFUSED | 它指定数据库查询被拒绝。 |

## 运行常数

| 常量代码 | 常数描述 |
| --- | --- |
| RTLD_LAZY | 它执行惰性绑定。默认情况下，Node.js 设置此标志。 |
| RTLD_NOW | 它在 `dlopen(3)` 返回之前解决了库中所有未定义的符号。 |
| RTLD_GLOBAL | 由库定义的这些符号将可用于随后加载的库的符号解析。 |
| RTLD_LOCAL | `RTLD_GLOBAL` 的反义词。如果两个标志都没有指定，这是默认行为。 |
| RTLD_DEEPBIND | 这使得一个独立库优先使用它自己的符号，而不是以前加载的库中的符号。 |

## 优先级常数

| 常数代码 | 常数描述 |
| --- | --- |
| PRIORITY_LOW | 最小进程调度优先级。 |
| PRIORITY_BELOW_NORMAL | 进程调度优先级低于 `PRIORITY_NORMAL`，高于 `PRIORITY_LOW`。 |
| PRIORITY_NORMAL | 进程调度优先级为正常或默认。 |
| PRIORITY_ABOVE_NORMAL | 进程调度优先级低于 `PRIORITY_HIGH`，高于 `PRIORITY_NORMAL`。 |
| PRIORITY_HIGH | 优先级低于最高和高于正常的进程调度优先级。 |
| PRIORITY_HIGHEST | 进程调度优先级最高。 |

## libuv 常数

| 常数代码 | 常数描述 |
| --- | --- |
| UV_UDP_REUSEADDR |  |

## 示例

下面的例子说明了 `os.constants` 在 Node.js 中的使用：

### 例 1

```js
// Import os module
const os = require('os');

constants = os.constants;

// Printing all os.constants
console.log(constants);
```

**输出:**

```js
[Object: null prototype] {
  UV_UDP_REUSEADDR: 4,
  dlopen: [Object: null prototype] {},
  errno:
   [Object: null prototype] {
     E2BIG: 7,
     EACCES: 13,
     EADDRINUSE: 100,
     . . .
     PRIORITY_HIGH: -14,
     PRIORITY_HIGHEST: -20 } }
```

### 例 2

```js
// Import os module
const os = require('os');

constants = os.constants;

// Printing os.constants

// Signals constants
if(constants.signals != undefined){
    console.log("Signals:");
    console.log(constants.signals);
}

// Priority constants
if(constants.priority!=undefined){
    console.log("priority:");
    console.log(constants.priority);
}
```

**输出:**

```js
Signals:
[Object: null prototype] {
  SIGHUP: 1,
  SIGINT: 2,
  . . .
  PRIORITY_HIGH: -14,
  PRIORITY_HIGHEST: -20 }
```

**注意:** 以上程序使用 `node index.js` 命令编译运行。

**参考:** [https://nodejs.org/api/os.html#os_os_constants](https://nodejs.org/api/os.html#os_os_constants)