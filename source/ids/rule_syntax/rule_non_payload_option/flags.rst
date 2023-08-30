flags
=====

``flags`` 规则选项检查TCP头中是否设置了指定的标志位。

可以检查以下标志位：

* A -> Accurate ECN
* C -> Congestion Window Reduced
* E -> ECN-Echo
* U -> Urgent
* K -> ACK(Acknowledgment)
* P -> Push
* R -> Reset
* S -> Syn
* F -> Fin
* 0 -> No TCP flags set

可以通过指定多个标志字符一次查看多个标志。这样做告诉SIFLOW-IDS查找选项中指定的所有标志。

此外，规则选项还可以包括以下可选修饰符之一，以更改评估标准的方式：

* + ->匹配任何指定的位，以及任何其他位
* * ->匹配（如果设置了任何指定位）
* !-如果未设置指定的位，则>匹配

**格式:**

.. code::

 flags:[*modifier*]*test_flag*…[,*mask_flag*…];
 
**例子:**

.. code::

 flags:SA;
 
.. code::

 flags:*SA;
 
.. code::

 flags:SF,CE;