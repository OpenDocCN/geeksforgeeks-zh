# 用 5 个简单的步骤编译我们自己的安卓内核

> 原文：[https://www.geeksforgeeks.org/compile-our-own-android-kernel-in-5-simple-steps/](https://www.geeksforgeeks.org/compile-our-own-android-kernel-in-5-simple-steps/)

[安卓内核](https://www.geeksforgeeks.org/introduction-to-android-development/)帮助应用程序与设备的硬件组件进行通信。

比如：

1.  我们大多数人都熟悉`game mode`。它的功能是指示处理器和图形处理单元以最大频率运行。
2.  另一个例子是`power saving mode`。它指示处理器和图形处理单元以最低频率运行。

## 需要编译我们自己的内核

编译我们自己的内核可能会非常有用，因为：

*   使用我们自己的内核。
*   可以根据需要进一步优化用户体验，这也有助于[开源开发](https://www.geeksforgeeks.org/contributing-to-open-source-getting-started/)。

## 编译我们自己的内核的步骤

### 先决条件

以下是编译我们自己的安卓内核的先决条件：
*   [Ubuntu 或任何其他基于 Linux 的操作系统](https://www.geeksforgeeks.org/introduction-to-linux-operating-system/)
*   熟悉[基本的 Linux 命令](https://www.geeksforgeeks.org/linux-commands/)
*   熟练使用 [Git 和 Github](https://www.geeksforgeeks.org/ultimate-guide-git-github/)
*   设备的[源代码](https://www.geeksforgeeks.org/language-processors-assembler-compiler-and-interpreter/)
*   打开终端并粘贴如下命令：

```bash
sudo apt-get install \
    git ccache automake flex lzop bison \
    gperf build-essential zip curl \
    zlib1g-dev zlib1g-dev:i386 \
    g++-multilib python-networkx \
    libxml2-utils bzip2 libbz2-dev \
    libbz2-1.0 libghc-bzlib-dev \
    squashfs-tools pngcrush \
    schedtool dpkg-dev liblz4-tool \
    make optipng maven libssl-dev \
    pwgen libswitch-perl policycoreutils \
    minicom libxml-sax-base-perl \
    libxml-simple-perl bc \
    libc6-dev-i386 lib32ncurses5-dev \
    x11proto-core-dev libx11-dev \
    lib32z-dev libgl1-mesa-dev xsltproc unzip
```

### 下载所需文档

*   在本地磁盘上克隆设备源码：

```bash
mkdir mykernel
git clone {link to your device kernel source}
```

*   下载兼容的 [GCC](https://www.geeksforgeeks.org/builtin-functions-gcc-compiler/) 工具链。本文使用 AOSP 的 GCC。

```bash
cd mykernel
git clone https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/aarch64/aarch64-linux-android-4.9 toolchain
```

*   下载兼容的 CLANG 工具链。本文使用 [AOSP](https://android.googlesource.com/platform/prebuilts/clang/host/linux-x86/+archive/android-9.0.0_r48/clang-4691093.tar.gz) 的 Clang。
*   将下载的文件移动到`mykernel`文件夹，然后使用以下命令解压：

```bash
tar vxzf linux-x86-android-9.0.0_r48-clang-4691093.tar.gz
```

### 编译内核

```bash
cd mykernel
rm -rf out
mkdir out
export ARCH=arm64
export SUBARCH=arm64
export DTC_EXT=dtc

make O=out ARCH=arm64 {device defconfig}

PATH="${PWD}/bin:${PWD}/toolchain/bin:${PATH}" \
make -j$(nproc --all) O=out \
                      ARCH=arm64 \
                      CC=clang \
                      CLANG_TRIPLE=aarch64-linux-gnu- \
                      CROSS_COMPILE=aarch64-linux-android- \
                      | tee kernel.log
```

在这里，将`{device defconfig}`替换为您的配置文件的名称。您可以在`/arch/arm64/configs`文件夹中找到它。

### 启动编译好的内核

*   浏览到`/out/arch/ARM64/boot`，找到`image-DTB file`（编译好的 zImage）并复制它。
*   下载 [Android 镜像厨房](https://forum.xda-developers.com/showthread.php?t=2073775)并反编译您的原厂启动镜像。反编译后，您会在反编译文件夹中找到原厂内核。用之前复制的文件替换它，然后重新编译启动镜像。
*   使用以下命令通过 [Fastboot](https://dl.google.com/android/repository/platform-tools-latest-linux.zip) 刷入：

```bash
fastboot flash boot mykernel.img
```

### 处理中遇到的错误

`mykernel`文件夹中会生成一个`kernel.log`文件。找到错误行并寻找解决方案。另外，在论坛发帖求助时，请不要忘记附上日志文件。

这将是一个基本的内核，一旦它成功启动，就可以添加更多的功能。