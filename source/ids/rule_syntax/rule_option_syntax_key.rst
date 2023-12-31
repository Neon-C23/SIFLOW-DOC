规则选项语法键
==============

单星号字符串
------------

被单个星号包裹起来的字符串用作任意值的占位符。当看到此选项时，他们必须将其替换为适当的值。

请务必注意，单星号字符串可以是不同类型数据（如字符串或整数）的占位符，因此在指定一个或多个值时必须确保考虑到这一点。

在下面的示例中，用户必须写入 ``msg`` 后跟一个 ``message`` 值。

msg:"*message*"

例:

.. code::
 
 msg:"这是一条消息"
 
 
 
方括号
------

方括号 ``[]`` 表示随附的一个或多个项目是可选的。如果方括号中的项目在竖线字符 ``|`` 之间分隔，则规则编写者可以选择其中一个项目，也可以不选择任何项目。

在下面的示例中，规则编写者可以选择 ``pizza`` 或 ``cookies`` ，也可以不选择其中任何一个。

.. code::
 
 [pizza|cookies]
 
在以下示例中，规则编写器可以选择添加字符串。 ``, nocase``

.. code::

 [, nocase]
 

 
 
大括号
------

大括号 ``{}`` 表示规则编写者必须选择由竖线字符分隔的一个（但只能选择一个）。

在下面的示例中，规则编写者必须选择其中一个 ``pizza`` 或 ``cookies`` ，但不能同时选择两者。

.. code::

 {pizza|cookies}
 
 

三个点省略符
------------

三个点 ``...`` 表示规则选项、规则选项参数或其他修饰符可以重复任意次数。省略号适用于它所在的整个组，无论是大括号组还是方括号组。

在下面的示例中，规则编写者必须指定字符串food以及以逗号分隔的任意数量的 *food* 项。

.. code::

 food *food*[, *food*]...

例如，这将是一个有效的条目:

.. code::

 food pizza, cookies, bacon