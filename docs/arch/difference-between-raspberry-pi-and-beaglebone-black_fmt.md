# 树莓派和BeagleBone Black的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-raspberry-pi-and-beaglebone-black/](https://www.geeksforgeeks.org/difference-between-raspberry-pi-and-beaglebone-black/)

## 1. 树莓派
树莓派是一款价格较低的迷你电脑，具有信用卡的物理尺寸。它运行多种风格的 Linux，可以操作几乎所有普通计算机可以完成的任务。树莓派还支持通过通用输入/输出引脚连接传感器和执行器。由于树莓派运行 Linux 操作系统，支持 Python “开箱即用”。它还提供了一组通用输入/输出（GPIO）引脚，使您能够管理物理计算的数字组件，并探索物联网（IoT）。

## 2. BeagleBone Black
BeagleBone Black 是一款开放式硬件单板计算机，由德州仪器开发。虽然它可以与树莓派相媲美，但 BeagleBone Black 的目标是一个不同的市场。与其关注业余爱好者，它更像是一个专注于工程的板子。

## 树莓派和BeagleBone Black的区别

| 参数 | 树莓派 | BeagleBone Black |
| :--- | :--- | :--- |
| 模型版本 | 它使用 B 型版本。 | 它使用 A5 版本。 |
| 处理器类型 | 它使用的是 ARM11 处理器。 | 它使用的是 ARM Cortex-A8 处理器。 |
| 随机存取存储 | 对于树莓派的功能，使用了 512 MB 的 SDRAM。 | 对于 BeagleBone Black 的功能，使用 512 MB 的 DDR3L。 |
| 处理器速度 | 它使用 700 MHz 进行处理。 | 它使用 1 GHz 进行处理。 |
| 存储 | 它有专门的 SD 卡插槽来装载操作系统。 | 它使用 4GB（micro SD）来加载操作系统和数据存储。 |
| 功耗 | 它需要 700 mA（3.5W）的电源。 | 它需要 210 mA（1.05 W）的最小功率才能工作。 |
| GPIO 引脚 | 它有 12 个 GPIO 引脚。 | 它有 69 个 GPIO 引脚。 |
| 开发环境 | 它使用 IDLE、Scratch、Squeak/Linux 来执行任务。 | 它使用 Python、Scratch、Squeak、Cloud9/Linux 来执行特定的任务。 |
| USB 主机 | 它板上有 2 个 USB 2.0。 | 它的主板上有 1 个 USB 2.0。 |
| 音频输出 | 支持高清多媒体接口，模拟音频输出。 | 它使用模拟输出音频。 |
| 视频输出 | 它支持高清多媒体接口，视频合成输出。 | 没有这样具体的视频输出。 |
| 通用非同步收发传输器 | 它使用 1 个 UART 发送和接收串行数据。 | 它使用 5 个 UART 发送和接收串行数据。 |
| 输入/输出引脚数量 | 它有 8 个数字、0 个模拟引脚。 | 它有 65 个数字引脚，7 个模拟引脚。 |