pkt_data
========

规则选项 ``pkt_data`` 将检测光标设置为规范化数据包数据的起始位置。

不包含任何缓冲区说明符的规则将默认检查有效负载选项是否与 ``pkt_data`` 缓冲区匹配。
然而，人们可能希望显式使用 ``pkt_data`` 缓冲区，用于澄清目的，或者在使用其他粘性缓冲区后将光标返回到规范化的数据包数据。

**格式:**

.. code::

 pkt_data;
 
**例子:**

.. code::

 pkt_data;
 content:"pizza", depth 5;
 pkt_data;
 content:"AAAAAA";
 bufferlen:>1000;