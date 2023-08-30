.. SI-WAF功能的介绍及目录

WAF
======

WAF（Web应用防火墙）是一种专门为Web应用程序提供保护的防火墙，它通过执行一系列针对HTTP/HTTPS的安全策略来实现这一目的。它与传统防火墙不同，它是工作在应用层的防火墙，主要针对Web请求/响应进行防护。

需要注意的是，因为SIFLOW是旁路监听抓取流量来进行分析的，因此SI-WAF无法对HTTP/HTTPS流量访问进行阻断以及改写等操作，仅能在匹配规则检测到攻击后做出告警。

.. toctree::
   :maxdepth: 2
   
   configuration
   rule_writing_syntax