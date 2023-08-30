regex
=====

规则选项``regex``通过Google RE2引擎将正则表达式与有效负载数据进行匹配。

还可以在正则表达式后面添加``relative``参数来相对于先前光标移动进行检查匹配。

RE2语法详见：https://github.com/google/re2/wiki/Syntax

**格式:**

.. code::

 regex:"*regex_string*"[,relative];
 
**例子:**

.. code::
 
 regex:"^[a-zA-Z][a-zA-Z0-9_]*$", relative;
 
.. code::
 
 regex:"^[a-zA-Z][a-zA-Z0-9_]*$";