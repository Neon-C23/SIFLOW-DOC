md5、sha256、sha512
===================

这里有三个“hash”选项，每个选项都用于检查某些有效负载数据与哈希值：``md5``、``sha256`` 和 ``sha512``。

每个选项需要两个参数：用双引号括起来的实际哈希值和从有效负载中获取哈希值的字节数。此外，用户还可以指定一个偏移量 ``offset`` 参数来检查特定位置的字节，或者使用 ``relative`` 参数来相对于当前光标位置对字节进行哈希。

偏移量值可以是 -65535:65535 之间的整数。

最后，每个哈希选项都可以通过在哈希值前面放置一个``!``来取反。

所有三个选项的结构都相同，唯一的区别是选项名称。

MD5
---

**格式:**

.. code::

 md5:[!]"*hash*", length *length*[, offset *offset*][, relative];

**例子:**

.. code::

 md5:"7cf2db5ec261a0fa27a502d3196a6f60", length 100, offset 0, relative;

SHA256
------

**格式:**

.. code::

 sha256:[!]"*hash*", length *length*[, offset *offset*][, relative];
 
 
**例子:**

.. code::

 sha256:"9ed1515819dec61fd361d5fdabb57f41ecce1a5fe1fe263b98c0d6943b9b232e", length 100, offset 0, relative;
	   
SHA512
------

**格式:**

.. code::

 sha512:[!]"*hash*", length *length*[, offset *offset*][, relative];
 
*例子:*

.. code::

 sha512:"d8fefb4255686e6bf365b0f4763fad983f624beb7cbbb59b617c745c346b8db51a870fe0a89cfba036cfbf2d011686b881acd8ab3278b318a304227ac2a99072", length 100, offset 0, relative;