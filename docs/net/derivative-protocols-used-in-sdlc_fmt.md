# SDLC 中使用的衍生协议

> 原文：[https://www.geeksforgeeks.org/derivative-protocols-used-in-sdlc/](https://www.geeksforgeeks.org/derivative-protocols-used-in-sdlc/)

尽管**高级数据链路控制(HDLC)** 是**同步数据链路控制(SDLC)** 的子集，但 SDLC 最初是在 HDLC 之前由 IBM 创建的。

SDLC 是第一个完全基于同步、面向比特操作的链路层协议。SDLC 基本上是 HDLC 的前身。SDLC 基本上执行各种功能，例如：

*   它用于通过链路传输数据或信息单元。
*   它还管理链接级流。
*   它还管理传输过程中可能出现的错误的错误恢复和纠错过程。

**SDLC 支持的物理链路：**
SDLC 高度支持的物理链路有多种类型，如下所示：

*   **数据通道 –**
    这些通道用于在并行管理器中传输或传输位，因为这些通道连接的节点应该彼此非常靠近。
*   **SDLC link –**
    这是将远程节点连接在一起的最常见和最广泛使用的方法。
*   **X.25 Interface –**
    在这种接口下，远程节点也可以通过称为 `QLLC`（合格逻辑链路控制）的协议在分组交换网络上连接，以承载 SDLC 帧。

## 衍生协议

有很多非常流行的协议，都是从 SDLC 协议衍生而来的。这些协议由许多标准机构标准化。

下面给出了一些简单基于 SDLC 的重要衍生协议：

1.  **Link Access Procedure, Balanced (LAPB) –**
    `LAPB` 用于实现[数据链路层(DLL)](https://www.geeksforgeeks.org/framing-in-data-link-layer/)，如 X.25 协议套件中所描述和定义。`LAPB` 是 X.25 协议栈中最为人熟知和流行的协议。它是一种可靠的同步串行协议，主要用于管理 DTE 和 DCE 站点之间的数据包成帧。

    它是一种面向比特的协议，源自 `HDLC`，用于确保所有数据帧无错误且顺序正确。它与 `SDLC` 和 `HDLC` 共享相同的帧格式、帧类型和不同字段的功能。顾名思义，`LAPB` 是一种平衡协议，通常在 `ABM`（异步平衡模式）下运行。

2.  **High-Level Data Link Control (HDLC) –**
    `HDLC` 是由[国际标准化组织(ISO)](https://www.geeksforgeeks.org/iso-full-form/)采用的标准。它是一种面向比特、代码透明的 `SDLC` 协议，由 ISO 开发。`HDLC` 和 `SDLC` 共享相同的帧格式。`HDLC` 字段也提供与 `SDLC` 中类似的功能。

    `HDLC` 通常提供两种服务，即面向连接和无连接。它通常支持三种不同类型的数据传输模式，即 `NRM`（正常响应模式）、`ABM`（异步平衡模式）和 `ARM`（异步响应模式）。但是它不支持环路和集线器先行配置。思科路由器也使用它通过租用线路进行串行通信，作为点对点协议(`PPP`)的替代方式。

3.  **Logical Link Control (LLC) –**
    `LLC` 基本上是由 `IEEE 802.2` 开发的。它通常用于在局域网(`LAN`)上提供 `HDLC` 风格的服务。它是局域网中非常流行的数据链路协议。`LLC` 是 `HDLC` 的子集。它使用 `HDLC` 的异步平衡模式(`ABM`)子类。`LLC` 通常提供流量控制和 `ARQ`（自动重传请求）错误管理技术。

    `LLC` 基本上有三个版本，如下所示：
    *   ㈠. 物理服务标题(`PSH`)
    *   ㈡. 合格逻辑链路控制(`QLLC`)
    *   ㈢. 增强型逻辑链路控制(`ELLC`)

4.  **合格逻辑链路控制(QLLC) –**
    `QLLC` 是 IBM 定义的 `DLL` 协议，它只允许 `SNA`（系统网络体系结构）数据通过 `X.25` 网络传输。它还提供传输 `SNA` 数据非常需要的数据链路控制能力。`QLLC` 和 `X.25` 一起取代了 `SNA` 协议中的 `SDLC`。`QLLC` 是 `LLC` 的翻版。