content
=======

我们将讨论的第一个选项是``content``，它用于对数据包数据执行基本模式匹配。此选项使用``content``关键字声明，后跟``:``字符，最后跟随双引号中的内容字符串。匹配也可以用``!``字符立即在冒号后“否定”，告诉SIFLOW-IDS仅处理不包含某些字符串或十六进制序列的数据包。

Content匹配可以包含ASCII字符串、十六进制字节或两者混合。十六进制字节必须用``|``字符括起来。

规则可以包含多个content匹配，每个匹配按照它们在规则中声明的顺序进行评估。这当然意味着只要``content``检查继续通过，SIFLOW-IDS将继续检查数据包数据中的后续匹配。因此，将最独特的序列匹配放在规则顶部通常是有益的，提高检测效率。

**格式:**

 content:[!]"content_string";

**例子:**

.. code::

 # Simple ascii string match
 content:"USER root";
 
.. code::
 
 # Combining of ascii characters and hex bytes
 content:"PK|03 04|";
 
.. caution::

 某些字符必须转义（使用'\'字符）或以十六进制编码。它们是：';'、'\'和'"'。
 
内容匹配修饰符
--------------

可以使用选项修饰符编写SIFLOW-IDS内容匹配，以为给定的内容匹配设置额外的评估要求，从而在定义规则参数时为用户提供更大的特异性。

这些修饰符包括 nocase、within、 distance、 offset和 depth，它们与内容字符串一起编写，用逗号分隔。某些修饰符还需要“参数”来定义参数以配合它们。

**例子:**

.. code::

 content:"pizza", nocase; 
 
.. code::
 
 content:"cheese";

.. code::

 content:" pizza", within 6;