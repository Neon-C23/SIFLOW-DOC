.. IDS规则编写语法介绍

规则编写指南
============

SIFLOW的入侵检测依赖于SI-IDS规则的存在来保护网络，这些规则由两个主要部分组成：
* 规则标头定义对任何匹配流量执行的操作，以及规则应应用到的协议、网络地址、端口号和流量方向。
* 规则正文部分定义与给定规则关联的消息，最重要的是定义规则匹配需要满足的有效负载和非有效负载条件。尽管规则选项不是必需的，但它们对于确保给定规则以正确的流量为目标至关重要。
以下是具有正确规则标头和规则选项定义的完全格式的 SIFLOW IDS 规则的示例: 

.. code:: 

 alert tcp $EXTERNAL_NET 80 -> $HOME_NET any \
 ( \
 sid:1; \
 msg:"Attack attempt!"; \
 content:"1337 hackz 1337", nocase, offset 6; \
 rem: "检查原始包数据"; \
 raw_data; \
 content:!"hello world!|61 37 56|"; \
 )

下面将详细讲解ids规则的各个部分的配置以及支持的规则选项:

.. toctree::
   :maxdepth: 2
   
   rule_syntax/rule_header
   rule_syntax/rule_option_syntax_key
   rule_syntax/rule_general_option
   rule_syntax/rule_payload_option
   rule_syntax/rule_non_payload_option
   
END