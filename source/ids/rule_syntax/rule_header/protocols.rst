协议
====

协议字段告诉SIFLOW-IDS给定规则应该查看哪种类型的协议，当前支持的协议包括：

* ip
* icmp
* tcp
* udp

一个规则只能设置一个协议，协议的名称放在操作之后。

**例子:**

.. code::

 alert udp $EXTERNAL_NET any -> $HOME_NET 53 (
 
.. code::
 
 alert tcp $EXTERNAL_NET any -> $HOME_NET 80 (