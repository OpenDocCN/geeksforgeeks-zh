# 如何使用 ipaddress 模块在 Python 中操纵 IP 地址？

> 原文: [https://www.geeksforgeeks.org/how-to-manipulate-ip-addresses-in-python-using-ipaddress-module/](https://www.geeksforgeeks.org/how-to-manipulate-ip-addresses-in-python-using-ipaddress-module/)

IP 地址代表互联网协议地址。这是与所选计算机或网络相关的识别号。当连接到网络时，该 IP 地址允许计算机发送和接收信息。Python 提供了 `ipaddress` 模块，该模块提供了在 IPv4 和 IPv6 地址和网络上创建、操作和操作的能力。这个模块内置了 Python 3.3+，所以如果你有 Python 3.3+，就不需要安装它了。虽然可以用 `pip` 安装。

```py
pip install ipaddress
```

该模块有 `IPv4Address` 类和 `IPv6Address` 类，分别处理 IPv4 和 IPv6 格式。由于 `IPv4Address` 和 `IPv6Address` 对象共享许多公共属性，我们将只在 IPv4 格式中查看，同样这些属性也可以在 IPv6 格式中看到。

## IPv4Address

IPv4 地址对象对于 IP v4 地址有很多属性。`ipaddress.IPv4Address('Address')` 构造一个表示 IPv4 地址 'address' 的 `IPv4Address` 对象。该类的一些属性如下：

*   `max_prefixlen`: 返回 `IPv4Address` 对象表示的 IP 地址中的总位数（IPv4 为 32，IPv6 为 128）。
*   `is_multicast`: 如果该地址是为多播使用而保留的，则返回 `True`。
*   `is_private`: 如果地址是为专用网络分配的，则返回 `True`。
*   `is_global`: 如果地址是为公共网络分配的，则返回 `True`。
*   `is_unspecified`: 如果地址未指定，则返回 `True`。
*   `is_reserved`: 如果地址是 IETF 保留的，则返回 `True`。
*   `is_loopback`: 如果这是一个环回地址，返回 `True`。
*   `is_link_local`: 如果地址是为链路本地使用而保留的，则返回 `True`。

我们还可以使用比较运算符来比较地址对象。此外，我们可以从地址对象中添加或减去整数。

现在让我们看一个这些属性的例子。

**例：**

```py
import ipaddress
# Creating an object of IPv4Address class and
# initializing it with an IPv4 address.
ip = ipaddress.IPv4Address('112.79.234.30')

# Print total number of bits in the ip.
print("Total no of bits in the ip:", ip.max_prefixlen)

# Print True if the IP address is reserved for multicast use.
print("Is multicast:", ip.is_multicast)

# Print True if the IP address is allocated for private networks.
print("Is private:", ip.is_private)

# Print True if the IP address is global.
print("Is global:", ip.is_global)

# Print True if the IP address is unspecified.
print("Is unspecified:", ip.is_unspecified)

# Print True if the IP address is otherwise IETF reserved.
print("Is reversed:", ip.is_reserved)

# Print True if the IP address is a loopback address.
print("Is loopback:", ip.is_loopback)

# Print True if the IP address is Link-local
print("Is link-local:", ip.is_link_local)

# next ip address
ip1 = ip + 1
print("Next ip:", ip1)

# previous ip address
ip2 = ip - 1
print("Previous ip:", ip2)

# Print True if ip1 is greater than ip2
print("Is ip1 is greater than ip2:", ip1 > ip2)
```

**输出：**

```py
Total no of bits in the ip: 32
Is multicast: False
Is private: False
Is global: True
Is unspecified: False
Is reversed: False
Is loopback: False
Is link-local: False
Next ip: 112.79.234.31
Previous ip: 112.79.234.29
Is ip1 is greater than ip2: True
```

## IPv4Network

IPv4 网络对象用于检查和定义 IP 网络。地址对象的所有属性对网络对象也有效，此外，网络对象还提供了附加属性。下面列出了其中的一些。

*   `network_address`: 返回网络的网络地址。
*   `broadcast_address`: 返回网络的广播地址。网络上的每个主机都应接收发送到广播地址的数据包。
*   `netmask`: 返回网络的网络掩码。
*   `with_netmask`: 返回网络的字符串表示，掩码以网络掩码表示。
*   `with_hostmask`: 返回网络的字符串表示，以主机掩码符号表示。
*   `prefixlen`: 返回网络前缀的位长度。
*   `num_addresses`: 返回此网络的地址总数。
*   `hosts()`: 返回网络中可用主机的迭代器。可用主机是属于该网络的所有 IP 地址，除了网络地址本身和网络广播地址。
*   `overlaps(other)`: 如果网络部分或完全包含在其他网络中，或者其他网络完全包含在该网络中，则返回 `True`。
*   `subnet(prefixlen_diff)`: 根据参数值，返回定义当前网络的子网。`prefixlen_diff` 参数是一个整数，表示前缀长度应增加的量。
*   `supernet(prefix_diff)`: 返回包含此网络定义的超网，`prefix_diff` 是我们的前缀长度应减少的量。
*   `subnet_of(other)`: 如果此网络是 `other` 的子网，则返回 `True`（在 Python 3.7 中添加）。
*   `supernet_of(other)`: 如果此网络是 `other` 的超网，则返回 `True`（在 Python 3.7 中添加）。
*   `compare_networks(other)`: 将此 IP 网络与其他 IP 网络进行比较。在此比较中，仅考虑网络地址，而不考虑主机位。它返回 -1、0 或 1。

现在让我们看一个上述方法的例子。

**例：**

```py
import ipaddress

# Initializing an IPv4 Network.
network = ipaddress.IPv4Network("192.168.1.0/24")

# Print the network address of the network.
print("Network address of the network:", network.network_address)

# Print the broadcast address
print("Broadcast address:", network.broadcast_address)

# Print the network mask.
print("Network mask:", network.netmask)

# Print with_netmask.
print("with netmask:", network.with_netmask)

# Print with_hostmask.
print("with_hostmask:", network.with_hostmask)

# Print Length of network prefix in bits.
print("Length of network prefix in bits:", network.prefixlen)

# Print the number of hosts under the network.
print("Total number of hosts under the network:", network.num_addresses)

# Print if this network is under (or overlaps) 192.168.0.0/16
print("Overlaps 192.168.0.0/16:", network.overlaps(ipaddress.IPv4Network("192.168.0.0/16")))

# Print the supernet of this network
print("Supernet:", network.supernet(prefixlen_diff=1))

# Print if the network is subnet of 192.168.0.0/16.
print("The network is subnet of 192.168.0.0/16:",
      network.subnet_of(ipaddress.IPv4Network("192.168.0.0/16")))

# Print if the network is supernet of 192.168.0.0/16.
print("The network is supernet of 192.168.0.0/16:",
      network.supernet_of(ipaddress.IPv4Network("192.168.0.0/16")))

# Compare the ip network with 192.168.0.0/16.
print("Compare the network with 192.168.0.0/16:",
      network.compare_networks(ipaddress.IPv4Network("192.168.0.0/16")))
```

**输出：**

```py
Network address of the network: 192.168.1.0
Broadcast address: 192.168.1.255
Network mask: 255.255.255.0
with netmask: 192.168.1.0/255.255.255.0
with_hostmask: 192.168.1.0/0.0.0.255
Length of network prefix in bits: 24
Total number of hosts under the network: 256
Overlaps 192.168.0.0/16: True
Supernet: 192.168.0.0/23
The network is subnet of 192.168.0.0/16: True
The network is supernet of 192.168.0.0/16: False
Compare the network with 192.168.0.0/16: 1
```