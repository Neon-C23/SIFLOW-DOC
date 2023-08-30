ip_proto
========

``ip_proto`` 规则选项用于检查IP头的标识（protocol）字段值是否小于、大于、等于、不等于、小于或等于或大于或等于指定的整数值。此规则选项还可以使用 ``<>`` 范围运算符检查头的Protocol值是否在一系列数字之间，用于独占范围检查，或使用 ``<=>`` 范围运算符进行包容性检查。

**格式:**

.. code::

 单值匹配:
 ip_proto:[<|>|=|!|<=|>=]*ip_proto*;
 
.. code::

 多值匹配:
 ip_proto:*ip_proto_min*{<>|<=>}*ip_proto_max*;
 
**例子:**

.. code::

 ip_proto:6;	#check is tcp(6)