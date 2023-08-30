icmp_id
=======

``icmp_id`` 与 ``icmp_seq`` 类似，但是是用于检查ICMP ID值的规则选项。

**格式:**

.. code::

 单值匹配:
 icmp_id:[<|>|=|!|<=|>=]*icmp_id*;
 
.. code::

 多值匹配:
 icmp_id:*icmp_id_min*{<>|<=>}*icmp_id_max*;
 
**例子:**

.. code::

 icmp_id:0;