fragoffset
==========

``fragoffset`` 规则选项用于检查IP头中的IP分段偏移值是否小于、大于、等于、不等于、小于或等于或大于或等于指定的整数值。此规则选项还可以使用 ``<>`` 范围运算符检查头的分段偏移值是否在一系列数字之间，用于独占范围检查，或使用 ``<=>`` 进行包容性检查。

**格式:**

.. code::

 单值匹配:
 fragoffset:[<|>|=|!|<=|>=]*fragoffset*;
 
.. code::

 多值匹配:
 fragoffset:*fragoffset_min*{<>|<=>}*fragoffset_max*;
 
**例子:**

.. code::

 fragoffset:0;