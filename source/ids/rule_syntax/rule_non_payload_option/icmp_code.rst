icmp_code
=========

``icmp_code`` 与 ``icmp_seq`` 类似，但是是用于检查ICMP代码值的规则选项。

**格式:**

.. code::

 单值匹配:
 icmp_code:[<|>|=|!|<=|>=]*icmp_code*;
 
.. code::

 多值匹配:
 icmp_code:*icmp_code_min*{<>|<=>}*icmp_code_max*;
 
**例子:**

.. code::

 icmp_code:0;