.. SI-WAF配置方法介绍

配置文件
========

SI-WAF的配置文件目录为：
/etc/siflow/waf.conf

该文件内容为一个json，其基本的格式如下:

.. code:: json

 {
   "local":{
   },
   "remote":{
   }
 }

``local`` 中填写需要加载的本地的规则文件路径(可以是具体规则文件的路径，也可以是一个目录路径，当指定目录路径时将遍历其中的所有.rules为后缀的文件)。

``remote`` 中则填写需要加载的远程规则文件的uri路径以及key，key值将决定返回那些规则内容，或是是否返回规则内容。

示例：

.. code:: json

 {
   "local":{
	 "GROUP_1": [
	   "/etc/siflow/rules/test_1.rules",
	   "/etc/siflow/rules/test_2.rules"
	 ],
	 "GROUP_2": [
	   "/home/rules"
	 ]
   },
   "remote":{
	 "REMOTE_1": [
	   {"key": "", "uri": "https://mylas.top/rules/test_1.rules"}
	 ]
   }
 }

注：在该示例中，GROUP_1、GROUP_2、REMOTE_1均为用户自定义组名，该组名对于程序无实际意义，仅供配置编写者便于规则分组使用。