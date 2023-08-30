raw_data
========

规则选项 ``raw_data`` 将检测光标设置为原始数据包数据。它与 pkt_data 不同，因为它可能会忽略某些预处理和规范化。

**格式:**

.. code::

 raw_data;
 
**例子:**

.. code::
 
 raw_data;
 content:"|FF F1|";