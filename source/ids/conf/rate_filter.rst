RateFilter
===========

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
 
在``RateFilter``填写需要应用基于速率过滤的规则，例：

.. code:: json

 {
   "RateFilter":[
     {"sid": 1001, "new_action": "pass", "count": 10, "seconds": 60, "timeout": 60},
     {"sid": 1002, "new_action": "alert", "count": 10, "seconds": 60, "timeout": 60},
	 {"sid": 1003, "new_action": "pass", "count": 10, "seconds": 60, "timeout": 60, "track": "by_src", "apply_ip": "$EXTRA_NET"}
   ]
 }
 
| 上述例子的意义如下：
| 第一条配置表示在60秒内1001号规则产生10个告警之后在接下来的60秒内将其action修改为``pass``不再产生告警
| 第二条配置与第一条类似，只不过action是修改为``alert``
| 第三条配置与第一条一样，只不过他被限定于只对与``$EXTRA_NET``匹配的源ip生效

EventFilter选项编写规则
-----------------------

#. ``sid`` 是必须填写的参数，作用规则的唯一id
#. ``new_action`` 是必须填写的参数，表示过滤类型，可选值为 ``[pass | alert]``
#. ``count`` 是必须填写的参数，表示事件数（int）
#. ``seconds`` 是必须填写的参数，表示时间段（uint）
#. ``timeout`` 是必须填写的参数，表示超时时间段（uint）
#. ``track`` 是可选参数，可选值为 ``[by_src | by_dst]``
#. ``apply_ip`` 是可选参数，其填写规则与 :ref:`ip_dm` 一致
#. ``track`` 和 ``apply_ip`` 必须一起使用，否则都不要使用

END