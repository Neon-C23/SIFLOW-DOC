rem
===

规则选项 ``rem`` 用于在规则正文中传达任意注释。此选项对检测没有影响，应仅用于提供有关其所在规则的元信息。

此选项接受单个参数，即用双引号括起来的字符串。

**格式:**

.. code::

 rem:"*comment_string*";

**例子:**

.. code::

 rem:"check for a malicious URI string";
 pkt_data;
 content:"/php_backdoor.php"; 