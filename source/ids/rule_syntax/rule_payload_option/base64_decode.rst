base64_decode、base64_data
==========================

SIFLOW-IDS 可以通过 ``base64_decode`` 选项解码数据包有效负载中存在的 base64 编码数据。
如果发现 base64 编码数据，它将被解码，然后将 base64 解码后的数据放置在 ``base64_data`` 粘性缓冲区中。

base64_decode
-------------

``base64_decode`` 选项告诉SIFLOW-IDS确切哪些字节要解码为 base64, 如果成功解码将把数据存放在 ``base64_data`` 粘性缓冲区。

它可以接受两个可选参数:

.. code::
  
 offset *offset*   #在有效负载中查找要解码的 base64 数据的位置

.. code::
 
 relative   #应用相对于游标而不是缓冲区开始的偏移量

**格式:**

.. code::

 base64_decode:*bytes*[, offset *offset*][, relative];
 
**例子:**

.. code::

 base64_decode:64, relative;
 
.. code::

 base64_decode:64, offset 10, relative;
 
base64_data
-----------

``base64_data`` 选项将检测光标设置为base64解码的开头，作用与 ``pkt_data`` 、 ``raw_data`` 类似，前提是 ``base64_decode`` 实际上能够解码数据。

此选项不需要任何参数，但要求在其之前指定``base64_decode``。

**格式:**

.. code::

 base64_data;
 
**例子:**

.. code::
 
 base64_decode:40, relative;
 base64_data;
 content:"AAAA";