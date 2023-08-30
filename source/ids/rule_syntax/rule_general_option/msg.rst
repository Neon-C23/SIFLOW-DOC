msg
===

规则选项``msg``用于添加描述规则的消息。该消息应总结规则的用途，并将与规则生成的事件一起输出。

此选项仅接受单个参数：用双引号括起来的文本字符串，用于说明规则将匹配的流量类型。

``msg`` 通常是SIFLOW-IDS规则中出现的第一个。

.. caution::
 
 SIFLOW-IDS规则有一些保留字符（例如，``;``、``\``、``"``），规则编写者必须使用它们进行转义才能在规则的选项中使用它们。

**格式:**

.. code::

 msg:"*message*";
 
**例子:**

.. code::

 msg:"SERVER-WEBAPP /etc/inetd.conf file access attempt";
 msg:"Malicious file download attempt\;";