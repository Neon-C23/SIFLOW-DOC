.. IDS功能的介绍及目录

IDS
===

入侵检测系统(Intrusion Detection System，简称“IDS”)是一种对网络传输进行即时监视，在发现可疑传输时发出警报的网络安全设备。它与其他网络安全设备的不同之处便在于，IDS是一种积极主动的安全防护技术。

.. caution::

 启用ids需要使用 ``--ids_enable`` 命令行标志，如果额外需要保存ids日志到本地则使用 ``--ids_log2local`` 标志。

.. toctree::
   :maxdepth: 2
   
   configuration
   rule_writing_syntax
