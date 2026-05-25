# AIX 和惠普-UX 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-aix-and-hp-ux/](https://www.geeksforgeeks.org/difference-between-aix-and-hp-ux/)

## AIX
AIX 是 IBM 提供的一系列专有[操作系统](https://www.geeksforgeeks.org/introduction-of-operating-system-set-1/)。AIX 代表高级交互执行。最初它是为 IBM RT PC RISC 工作站设计的，后来它被用于各种硬件平台，如 IBM RS/6000 系列、基于 PowerPC 的系统、System-370 大型机、PS-2 个人计算机和苹果网络服务器。它是已通过开放集团 UNIX 03 标准认证的五个商业操作系统之一。AIX 的第一个版本于 1986 年推出。AIX 的最新稳定版本是 7.2。

## 惠普-UX
惠普-UX 是一个由惠普企业提供的封闭源码操作系统。这是一个类似 Unix 的操作系统，其设计基于 [Unix 系统](https://www.geeksforgeeks.org/introduction-to-unix-system/) V。基本上是为惠普电脑设计的。它的目标系统是服务器。它是已通过开放集团 UNIX 03 标准认证的五个商业操作系统之一。惠普-UX 的第一个版本于 1983 年推出。惠普-UX 的最新稳定版本是 11i-v3。它具有带有动态可加载模块的单片内核。

## AIX 和惠普-UX 的区别

| 特性 | AIX (Advanced Interactive Executive) | 惠普-UX (HP-UX) |
| :--- | :--- | :--- |
| **开发者/拥有者** | 由 IBM 开发并拥有。 | 由惠普企业开发并拥有。 |
| **首次推出** | 于 1986 年推出。 | 于 1983 年推出。 |
| **目标系统** | 服务器、网络连接存储和工作站。 | 服务器。 |
| **支持的架构** | `POWER`、`PowerPC-AS`、`PowerPC` 和 `Power ISA`。 | `PA-RISC` 和 `IA-64`。 |
| **内核类型** | 一体式。 | 带有动态可加载模块的单片式。 |
| **包管理** | `installp` 和 `RPM`。 | `SD` 或 `swinstall`。 |
| **更新管理** | 服务更新管理助理 (`SUMA`)。 | `SWA` (惠普-UX 软件助理)。 |
| **本机 API** | `SysV/POSIX`。 | `SysV/POSIX`。 |
| **首选许可** | 专有的。 | 专有的。 |
| **支持的文件系统** | `JFS`、`JFS2`、`ISO 9660`、`UDF`、`NFS`、`SMBFS` 和 `GPFS`。 | `VxFS`、`HFS`、`CDFS`、`EVFS`、`NFS` 和 `CIFS`。 |