命令行标志
==========

| ``--save_cert`` 启用此标志以将在流量中获取到的证书保存到本地，你可以指定保存路径否则将保存到默认路径 "/var/log/siflow/certificate"
| 例：``--save_cert=/home/cert`` 保存到"/home/cert"目录中

``--cstk`` or ``--cert_send_to_kafka`` 启用此标志以将在流量中获取到的证书与流量数据一并发送到kafka

``--disk_space_limit`` 启用此标志用于在证书保存的本地目录空间仅剩设定值时停止保存证书，此标志必须携带参数（单位 MB），默认只剩500mb停止保存

``--save_cert_chain`` 启用以保存整个证书链，否则只保存证书链中第一个证书

``--waf_enable`` 启用waf功能。请注意，在未启用此标志时程序仍然会尝试读取waf配置但是不进行规则匹配

``--waf_log2local`` 启用保存waf日志到本地目录"/var/log/siflow/waf/"

``--ids_enable`` 启用ids功能。请注意，在未启用此标志时程序仍然会尝试读取ids配置但是不进行规则匹配

``--ids_qr_mode`` 启用ids快速匹配模式，将在匹配第一个规则并产生日志后停止匹配以最大化程序效率。在未启用此标志时程序会尝试匹配所有的规则。

``--ids_log2local`` 启用保存ids日志到本地目录"/var/log/siflow/ids/"