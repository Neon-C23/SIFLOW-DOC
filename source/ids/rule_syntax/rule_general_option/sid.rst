sid
===

关键字``sid``唯一标识给定的SIFLOW-IDS规则。

每个规则必须添加``sid``规则选项，该规则选项接受单个参数，其参数是规则必须唯一的数值。

.. caution::

 SIFLOW-IDS保留值0-9999供内部规则使用，用户应当从10000开始使用。
 
**格式:**

.. code::

 sid:*signature_id*;

**例子:**

.. code::
 
 sid:10001;