# 网络管理领域

> 原文:[https://www.geeksforgeeks.org/areas-of-network-management/](https://www.geeksforgeeks.org/areas-of-network-management/)

为了将轶事场景置于结构化框架中，国际标准化组织(ISO)创建了一个网络管理模型。

## 网络管理领域

这些是网络管理领域，定义如下：

*   **Performance Management**
    量化、测量、报告、分析和控制不同网络组件的性能（例如，利用率和吞吐量）是性能管理的主要目标。这些组件包括单独的`devices`（例如，链路、路由器和主机），以及端到端的抽象，例如通过网络的路径。诸如[Simple Network Management Protocol (SNMP)](https://www.geeksforgeeks.org/simple-network-management-protocol-snmp/)之类的协议标准在互联网性能管理中扮演着核心角色。

*   **Fault Management**
    故障管理的目标是记录、检测和响应网络中的故障状况。故障管理与性能管理之间的界限是模糊的。
    故障管理用于管理对链路故障、主机故障或路由器硬件问题等故障的即时处理，这些问题也被称为瞬时网络故障。借助性能管理，`SNMP`协议在故障管理中扮演着重要角色。

*   **Configuration Management**
    配置管理允许跟踪托管网络上的设备以及硬件和软件配置。

*   **Accounting Management**
    计费管理允许指定、记录和控制用户及设备对网络资源的访问。使用配额、基于使用的收费以及资源访问权限的分配都属于计费管理。

*   **安全管理**
    ```
    安全管理的目标是根据一些定义明确的策略来控制对网络资源的访问。关键配送中心是网络管理的一个组成部分。
    使用防火墙监控外部网络接入点是另一个重要组成部分。
    ```