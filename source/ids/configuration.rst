.. IDS配置方法介绍

配置文件
========

IDS的配置文件目录为：
/etc/siflow/ids.conf

该文件内容为一个json，其基本的格式如下:

.. code:: json

 {
   "Variable":{
     "ip":{
	 },
	 "port":{
	 }
   },
   "RulePath":[
   ],
   "Reputation":{
     "blacklist":[
     ],
	 "whitelist":[
	 ]
   },
   "Suppress":[	
   ],
   "EventFilter":[
   ],
   "RateFilter":[
   ]
 }

下面详细介绍配置中的每一个配置项：

.. toctree::
   :maxdepth: 2
   
   conf/variable
   conf/rule_path
   conf/reputation
   conf/suppress
   conf/event_filter
   conf/rate_filter
   
END