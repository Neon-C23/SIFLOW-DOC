规则操作
========

规则操作告诉SIFLOW-IDS如何处理匹配的数据包。有两个基本操作：

* alert-> 对当前数据包生成警报
* pass->将当前数据包标记为已通过
* ati->应用程序流量识别规则标识

给定规则的所需操作是在规则中声明的第一件事。

**例子:**

.. code::

 alert http any any -> any any (msg:"Generate an alert"; sid:1;)

.. code::

 pass http any any -> any any (msg:"Pass this packet"; sid:2;)

.. code::

 ati tcp any any -> any 22 (sid:1001; msg:"SSH FLOW";)
