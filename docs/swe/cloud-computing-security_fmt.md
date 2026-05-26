# 云计算安全

> 原文：[`https://www.geeksforgeeks.org/cloud-computing-security/`](https://www.geeksforgeeks.org/cloud-computing-security/)

**先决条件：** [云计算](https://www.geeksforgeeks.org/cloud-computing/)

## 什么是云计算？

云计算是指应用、计算资源、存储、数据库、网络资源等计算服务的按需交付。通过互联网和按使用付费。目前，对云计算服务的需求正在增加，而对云计算技能的需求也在增加。它提供三种主要类型的服务模式，即 [`SaaS`](https://www.geeksforgeeks.org/cloud-based-services/)(软件即服务)、[`PaaS`](https://www.geeksforgeeks.org/cloud-based-services/)(平台即服务)和 [`IaaS`](https://www.geeksforgeeks.org/cloud-based-services/)(基础设施即服务)。从小型到大型组织都已经开始使用云服务，因此根据他们的需求，他们会选择不同的[云类型](https://www.geeksforgeeks.org/types-of-cloud/)，如公共云、私有云、混合云、社区云。

## 云计算中的安全性

云计算是当前要求最高的技术之一，从小到大的组织都开始使用云计算服务。如果有不同类型的云部署模型可用，并且云服务是根据要求提供的，例如维护内部和外部安全性以保持云系统的安全。云计算安全或云安全是一个重要的关注点，是指保护云环境、数据、信息和应用程序免受未经授权的访问、分布式拒绝服务攻击、恶意软件、黑客和其他类似攻击的行为。社区云：允许有限的组织或员工访问共享的云计算服务环境。

## 云计算安全规划

由于安全性是云实施中的一个主要关注点，因此组织必须基于以下一些因素来规划安全性，这些因素代表了云安全性规划所依赖的三个主要因素。

- Select resources that can be moved to the cloud and tested for their sensitivity risks.
- Consider the type of cloud.
- The risk of cloud deployment depends on the type and service mode of cloud.

## 云计算安全控制的类型

云计算安全控制有 4 种类型，即

1.  **[`deterrence control`](https://www.geeksforgeeks.org/cloud-computing-security/)**：威慑控制旨在防止对云系统的恶意攻击。当存在内部攻击者时，这些控制非常有用。
2.  **Preventive control**：预防性控制通过消除系统中的漏洞来增强系统抵抗攻击的能力。
3.  **Detection and control**：识别和响应安全威胁并进行控制。检测软件的一些例子是入侵检测软件和网络安全监控工具。
4.  **Corrective control**：这些控制在发生安全攻击时被激活。它们限制了攻击造成的损害。

## 云安全的重要性

对于向云过渡的组织来说，在选择云提供商时，云安全是一个必不可少的因素。攻击一天比一天强烈，因此安全需要跟上。为此，选择能够提供最佳安全性并根据组织的基础架构进行定制的云提供商至关重要。云安全有很多好处：

- **Centralized security**：集中式安全带来集中式保护。因为管理所有设备和端点不是一项容易的任务，云安全可以帮助做到这一点。这将增强流量分析和网络过滤，这意味着更少的策略和软件更新。
- **Reduce costs**：投资于云计算和云安全，硬件支出和管理人力更少。
- **Reduced management**：无需手动安全配置和持续的安全更新，更容易管理组织。
- **Reliability**：这些都非常可靠。只要获得适当授权，任何设备都可以从任何地方访问云。

当我们考虑云安全时，它包括各种类型的安全，如授权访问的访问控制、维护隔离数据的网络分段、编码数据传输的加密、修补易受攻击区域的漏洞检查、监视各种安全攻击的安全监控以及数据丢失期间备份和恢复的灾难恢复。

有不同类型的安全技术被实施以使云计算系统更加安全，例如 [`SSL`](https://www.geeksforgeeks.org/cloud-computing-security/)(安全套接字层)加密、基于多租户的访问控制、入侵检测系统、防火墙、渗透测试、令牌化、[`VPN`](https://www.geeksforgeeks.org/cloud-computing-security/)(虚拟专用网络)以及避免公共互联网连接等技术。

但是事情并没有我们想象的那么简单，即使实现了多种安全技术，对于云系统来说总会涉及到[安全问题](https://www.geeksforgeeks.org/security-issues-in-cloud-computing/)。由于云系统是通过互联网管理和访问的，因此在维护安全云的过程中会出现很多挑战。一些云安全挑战是：

- Control of cloud data
- Wrong configuration
- Changing workloads
- Access management
- disaster recovery