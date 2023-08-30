nocase, offset, depth, distance, and within
===========================================

nocase
------

默认情况下，内容匹配区分大小写，但内容修饰符``nocase``告诉SIFLOW-IDS忽略大小写并以不区分大小写的方式查找指定的字符串匹配。

**格式:**

.. code::
 
 nocase
 
**例子:**

.. code::

 content:"/index/vulnerable_endpoint.php",nocase;

.. caution::

 该选项也适用于十六进制字节;指定将在数据包中查找“A”或“a”。
 
offset
------

修饰符``offset``允许规则编写者指定从何处开始搜索相对于数据包或缓冲区开头的模式。因此，``offset 5`` 将告诉SIFLOW-IDS在有效负载的前 5 个字节之后查找指定的模式。

此关键字允许从 -65535 到 65535 的值。

**格式:**

.. code::

 offset {offset|variable_name}
 
**例子:**

.. code::

 content:"|FE|SMB", offset 4;
 
depth
-----

修饰符``depth``允许规则编写者指定在SIFLOW-IDS数据包或缓冲区中查找指定模式的距离。例如，设置为``depth 5``将告诉SIFLOW-IDS仅在有效负载的前 5 个字节内查找模式。

指定``depth``而不带偏移量将隐式查看有效负载的开头，因此在这些情况下无需指定``offset 0``。

所选值必须大于或等于内容字符串的长度，最大值为 65535。

**格式:**

.. code::

 depth *depth*
 
**例子:**

.. code::

 content:"|FE|SMB", depth 4, offset 4; 
 content:"PK|03 04|", depth 4; 

distance
--------

该关键字类似于``offset``，但相对于前面的内容匹配，而不是有效负载/缓冲区的开头。它告诉SIFLOW-IDS在查找此内容匹配之前在最后一个内容匹配后查看跳过 X 个字节。

此关键字允许从 -65535 到 65535 的值。

**格式:**

.. code::

 distance *distance*
 
**例子:**

.. code::

 content:"ABC"; 
 content:"EFG", distance 1;
 
within
------

``within`` 关键字与``depth``类似，但是相对于前一个内容匹配而不是有效载荷的开头。它告诉SIFLOW-IDS在上一个内容匹配的X个字节内查找此内容匹配。

指定``within``而不指定``distance``将隐式地立即在上一个内容匹配之后查找，因此在这些情况下无需指定额外的``distance 0``选项。

所选值必须大于或等于内容字符串的长度，最大值为65535。

**格式:**

.. code::

 within *within*

**例子:**

.. code::

 content:"ABC"; 
 content:"EFG", within 10;
 
.. code::

 content:"ABC"; 
 content:"EFG", distance 1, within 3;
 
.. code::
 
 content:"DEF"; 
 content:"GHI", within 3;