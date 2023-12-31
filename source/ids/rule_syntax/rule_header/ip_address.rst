.. _ip_dm:

IP地址
======

规则标头中的 IP 地址告诉 SIFLOW-IDS 给定规则应应用于哪些源和目标 IP 地址。仅当给定数据包的源和目标 IP 地址与该规则中设置的 IP 地址匹配时，规则才会匹配。

可以通过以下四种方式之一声明它们：

* 作为带有可选 CIDR 块的数字 IP 地址（例如, ``192.168.0.5,192.168.1.0/24``)
* 作为 SIFLOW-IDS 配置中定义的变量，用于指定一个网络地址或一组网络地址（例如, ``$EXTERNAL_NET,$HOME_NET`` 等)
* 关键字 ``any`` ，表示任何 IP 地址
* IP 地址、IP 地址变量和/或端口范围的列表，它们使用逗号分隔且不包含任何空格（例如, ``192.168.1.0/24,10.1.1.0/24``)

在单个规则标头中进行两个 IP 地址声明：在协议字段之后声明的源 IP 地址和在方向运算符之后声明的目标 IP 地址。

.. attention::

 IP地址声明也可以被否定，以告诉SIFLOW-IDS匹配除列出的IP地址之外的任何IP地址。此否定由运算符 ``!`` 完成。

**例子:**

.. code::

 alert tcp 192.168.1.0/24 any -> 192.168.5.0/24 any (
 
.. code::

 alert tcp $EXTERNAL_NET any -> $HOME_NET 80 (
 
.. code::

 alert tcp any any -> 192.168.1.3 445 (
 
.. code::
 
 alert tcp !192.168.1.0/24 any -> 192.168.1.0/24 23 (
 
.. code::
 
 alert tcp !192.168.1.0/24,!10.1.1.0/24 any -> 192.168.1.0/24,10.1.1.0/24 80 (