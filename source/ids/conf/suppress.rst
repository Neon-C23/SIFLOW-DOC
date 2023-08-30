Suppress
========

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
 
在``Suppress``填写需要阻止告警产生的规则，例：

.. code:: json

 {
   "Suppress":[
     {"sid": 1001},
	 {"sid": 1002, "track": "by_src", "apply_ip": "$EXTRA_NET"}
   ]
 }
 
| 上述例子的意义如下：
| 第一条配置将阻止 1001 号规则产生任何日志
| 第二条配置将阻止 1002 号规则产生任何日志，但被限定于只对与``$EXTRA_NET``匹配的源ip生效

Suppress选项编写规则
--------------------

#. ``sid`` 是必须填写的参数，作用规则的唯一id
#. ``track`` 是可选参数，可选值为 ``[by_src | by_dst]``
#. ``apply_ip`` 是可选参数，其填写规则与 :ref:`ip_dm` 一致
#. ``track`` 和 ``apply_ip`` 必须一起使用，否则都不要使用

END