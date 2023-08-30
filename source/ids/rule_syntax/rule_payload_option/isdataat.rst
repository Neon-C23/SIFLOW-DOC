isdataat
========

规则选项``isdataat``验证有效载荷数据是否存在于指定位置。

``isdataat`` 关键字后跟一个冒号字符，后跟一个数字，该数字表示在哪里查找数据包数据，最后可选地跟随，相对于告诉SIFLOW-IDS从先前的光标移动开始查找数据。

用户还可以在数字前放置``!``符号来指定否定的``isdataat``检查，以检查有效载荷中是否不存在特定数量的数据。

有效的``isdataat``数字为0到65535（含）。这意味着``isdataat: 0``检查当前光标位置至少有一个字节存在。

**格式:**

.. code::

 isdataat:[!]*location*[,relative];
 
**例子:**

.. code::

 isdataat:100;
 content:"USER"; 
 # 检查“USER”后至少 30 个字节，因为有效的 isdataat 数字从 0 开始
 isdataat:29,relative; 
 content:!"|0a|", within 30;