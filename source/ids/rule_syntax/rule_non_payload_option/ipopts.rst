ipopts
======

``ipopts`` 规则选项用于检查IP头中是否存在指定的IP选项。

有11个可供选择的 ``ipopts`` 参数，一个 ``ipopts`` 选项只能有一个参数。这些选项包括以下内容：

* rr: Record Route
* eol: End of Options List
* nop: No Operation
* ts: Time Stamp
* sec: Security
* esec: Extended Security
* lsrr: Loose Source Routing
* lsrre: Loose Source Routing (For MS99-038 and CVE-1999-0909)
* ssrr: Strict Source Route
* satid: Stream ID
* any: Any IP options are set

**格式:**

.. code::

 ipopts:{rr|eol|nop|ts|sec|esec|lsrr|lsrre|ssrr|satid|any};
 
**例子:**

.. code::

 ipopts:rr;