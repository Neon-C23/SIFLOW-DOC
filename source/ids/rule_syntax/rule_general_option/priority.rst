priority
========

该选项 ``priority`` 为给定规则分配严重性级别，以启用适当的事件优先级。

有效优先级为 1-2147483647，其中 1 表示最严重，2147483647 表示最不严重。

给定规则应只有一个 ``priority`` 声明。

**格式:**
 
.. code::
 
 priority:*severity_level*;
 
**例子:**

.. code::

 priority:1;
 priority:10;