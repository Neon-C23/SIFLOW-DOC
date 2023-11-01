Reputation
==========

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
 
在 ``Reputation`` 填写黑白名单ip地址列表，例：

.. code:: json

 {
   "Reputation":{
     "blacklist":[
	   "192.168.2.1/24,47.102.101.16",
	   "!HOME_NET"
	 ],
	 "whitelist":[
	   "47.102.101.16"
	 ]
   }
 }
 
此配置项用于配置 ``源IP`` 白黑名单，处于白名单中的ip地址将跳过规则检测和其它检测，处于黑名单中的ip地址也将跳过规则检测和其它检测并产生告警。

白名单的优先级高于黑名单，因此当同一个ip地址同时匹配白黑名单时将跳过任何检测并不会产生任何告警，合理的配置白黑名单将提高 **ids** 运行效率。

这里的ip地址填写规则与 :ref:`ip_dm` 一致
