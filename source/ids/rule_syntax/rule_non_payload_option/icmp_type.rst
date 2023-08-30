icmp_type
=========

``icmp_type`` 与 ``icmp_seq`` 类似，但是是用于检查ICMP类型值的规则选项。

**格式:**

.. code::

 单值匹配:
 icmp_type:[<|>|=|!|<=|>=]*icmp_type*;
 
.. code::

 多值匹配:
 icmp_type:*icmp_type_min*{<>|<=>}*icmp_type_max*;
 
**例子:**

.. code::

 icmp_type:0;