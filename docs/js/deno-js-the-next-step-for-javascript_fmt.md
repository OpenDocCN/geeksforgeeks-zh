# Deno.js: JavaScript 的下一步

> 原文: [https://www.geeksforgeeks.org/deno-js-the-next-step-for-javascript/](https://www.geeksforgeeks.org/deno-js-the-next-step-for-javascript/)

`Node.js`的创建者发现`Node`有很多缺陷，可以在这个视频中看到: https://www.youtube.com/watch?v=M3BM9TB-8yA。
他在2年前启动了一个名为`deno`的项目，这个项目是开源的，在`alpha`中。最近`deno 1.0`(生产就绪)于2020年5月13日发布。

`Javascript`已经从一种混乱的浏览器语言发展到一种用于应用程序全栈开发的服务器端健壮语言。但是进入`Node`的`JS`有很多缺陷，这些缺陷在未来几年会更新，但不会在`Node`中更新。`Node`的创建者决定构建类似`Node`的东西，但是没有所有这些缺陷。所以现在我们有了新的服务器端技术。

## Deno 特色

1.  `javascript`的现代特性，如`Promise`等。
2.  完全支持`TypeScript`，本机编译。因此，您可以利用像智能感知这样的功能。
3.  广泛的标准库。
4.  它具有标准的`ES模块`兼容性。
5.  没有包管理器，模块是通过网址导入的。
6.  一流的`await`支持。
7.  内置测试功能。
8.  浏览器兼容，而`Node`仅用于后端。(可以访问像`window`这样的类)

## 会取代 Node.js 吗？

不，`Node`现在是一项成熟的技术，在世界范围内被广泛使用。但是人们将开始走向`deno`，因为它本质上是`Node`，但更好。

## Node 和 Deno 的相似之处

*   两者都是基于`V8`铬发动机开发的。
*   两者都非常适合服务器端的`JavaScript`。

## 差异

*   `Node`是用`C++`和`JS`编写的，而`deno`是用`Rust`和`TypeScript`编写的。
*   `Node`有一个名为`npm`的包管理器，而在`deno`中，您可以从`URL`导入`ES模块`。
*   `Node`使用`CommonJS`语法，而`deno`使用官方的`ES模块`语法。
*   `Deno`在`API`和库中使用`Ecmascript`特性，而`Node`使用回调。
*   `Deno`有很好的安全特性，而`Node`允许访问任何东西。
*   `Deno`正在尝试用二进制编译。(但这不是一个生产就绪的特性)

## 承诺

`Node`是在`JS`有`Promises`或`async/await`之前实现的。`Node`与`promises`的对应物是`EventEmitter`，`Node`中的`API`就是基于它的。
而`Deno`的所有回调都源于`Promise`。

## Deno 沙盒

`Deno`创建了一个沙盒环境，只允许其`CLI`明确允许的系统调用。
当`Deno`试图复制浏览器实现的相同权限模型时，没有什么能阻止`Node`访问您磁盘上的私有文件并将其发送到服务器。
如果一个程序需要访问网络，我们必须像这样明确地给予它许可:

```shell
deno run --allow-net app.ts
```

## 一级 TypeScript 支持

`Deno`支持`TypeScript`，无需额外的工具。运行时的设计考虑到了`TypeScript`。`deno types`命令为`deno`提供的所有内容提供类型声明。`Deno`的标准模块都是用`TypeScript`编写的。

## 兼容性

`Deno`与现有的`JS`工具和`Node`包不兼容。但是正在努力使工具更加兼容。

## 格式化代码

您可以通过以下方式基于易于阅读的标准轻松格式化代码

```shell
Deno fmt app.ts
```

## 应该学 Deno 吗？

你应该从`JavaScript`开始，然后学习`Node`，然后只应该开始`deno`，因为事实是使用`Node`的公司不会轻易用`deno`替换它，因为它需要大量的资源。
`Node`将在行业内广泛应用。因此，第一步应该始终是学习`Node`，然后为尝试实现它的新客户端进行`deno`。

## 标准库

*   `archive`: `tar`存档实用程序。
*   `async`: 异步实用程序。
*   `bytes`: 帮助操作字节片。
*   `log`: 日志实用程序。
*   `mime`: 支持多部分数据。
*   `datetime`: 日期/时间解析。
*   `encoding`: 各种格式的编码/解码。
*   `flags`: 解析命令行标志。
*   `fmt`: 格式化和打印。
*   `node`: `Node.js`兼容层。
*   `path`: 路径操纵。
*   `ws`: `WebSockets`。
*   `fs`: 文件系统`API`。
*   `hash`: 加密库。
*   `http`: `HTTP`服务器。
*   `io`: `I/O`库。

## 让我们用 Deno 弄脏手

### 安装

```shell
# Using Shell (macOS, Linux):
$ curl -fsSL https://deno.land/x/install/install.sh | sh

# Using PowerShell (Windows):
$ iwr https://deno.land/x/install/install.ps1 -useb | iex

# Using Homebrew (macOS):
$ brew install deno

# Using Chocolatey (Windows):
$ choco install deno

# Using Scoop (Windows):
$ scoop install deno
```

### 入门

尝试运行一个简单的程序:

```shell
$ deno run https://deno.land/std/examples/welcome.ts
```

或者更复杂的:

```typescript
import { serve } from "https://deno.land/std@0.50.0/http/server.ts";
const s = serve({ port: 8000 });
console.log("http://localhost:8000/");
for await (const req of s) {
  req.respond({ body: "Hello World\n" });
}
```

您可以使用此命令获取`deno CLI`的手册

```shell
$ deno --help
```

```
deno 0.42.0
A secure JavaScript and TypeScript runtime

Docs: https://deno.land/std/manual.md
Modules: https://deno.land/std/ https://deno.land/x/
Bugs: https://github.com/denoland/deno/issues

To start the REPL, supply no arguments:
 deno

To execute a script:
 deno run https://deno.land/std/examples/welcome.ts
 deno https://deno.land/std/examples/welcome.ts

To evaluate code in the shell:
 deno eval "console.log(30933 + 404)"

Run 'deno help run' for 'run'-specific flags.

USAGE:
   deno [OPTIONS] [SUBCOMMAND]

OPTIONS:
   -h, --help
           Prints help information
   -L, --log-level <log-level>
           Set log level [possible values: debug, info]
   -q, --quiet
           Suppress diagnostic output
           By default, subcommands print human-readable
            diagnostic messages to stderr.
           If the flag is set, restrict these messages to errors.
   -V, --version
           Prints version information

SUBCOMMANDS:
   bundle      Bundle module and dependencies into single file
   cache       Cache the dependencies
   completions    Generate shell completions
   doc         Show documentation for a module
   eval        Eval script
   fmt         Format source files
   help        Prints this message or the help
                of the given subcommand(s)
   info        Show info about cache or info
                related to source file
   install     Install script as an executable
   repl        Read Eval Print Loop
   run         Run a program given a filename
               or url to the module
   test        Run tests
   types       Print runtime TypeScript declarations
   upgrade     Upgrade deno executable to newest version

ENVIRONMENT VARIABLES:
   DENO_DIR             Set deno's base directory
                        (defaults to $HOME/.deno)
   DENO_INSTALL_ROOT    Set deno install's output directory
                        (defaults to $HOME/.deno/bin)
   NO_COLOR             Set to disable color
   HTTP_PROXY           Proxy address for HTTP requests
                        (module downloads, fetch)
   HTTPS_PROXY          Same but for HTTPS
```