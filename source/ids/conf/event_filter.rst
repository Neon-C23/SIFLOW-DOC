EventFilter
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
 
在 ``EventFilter`` 填写需要应用告警过滤的规则，以减少事件产生量，例：

.. code:: json

 {
   "EventFilter":[
     {"sid": 1001, "type": "limit", "count": 10, "seconds": 60},
     {"sid": 1002, "type": "threshold", "count": 10, "seconds": 60},
     {"sid": 1003, "type": "both", "count": 10, "seconds": 60},
     {"sid": 1004, "type": "limit", "count": 10, "seconds": 60, "track": "by_src", "apply_ip": "$EXTRA_NET"}
   ]
 }
 
| 上述例子的意义如下：
| 第一条配置表示在60秒内1001号规则至多能产生10个告警
| 第二条配置表示在60秒内每匹配成功1002号规则10次则产生一次告警
| 第三条配置表示在60秒内匹配成功1003号规则10次时则产生一次告警，然后之后不再产生告警
| 第四条配置与第一条配置类似，只不过他被限定于只对与 ``$EXTRA_NET`` 匹配的源ip生效

EventFilter选项编写规则
-----------------------

#. ``sid`` 是必须填写的参数，作用规则的唯一id
#. ``type`` 是必须填写的参数，表示过滤类型，可选值为 ``[limit | threshold | both]``
#. ``count`` 是必须填写的参数，表示事件数（int）
#. ``seconds`` 是必须填写的参数，表示时间段（uint）
#. ``track`` 是可选参数，可选值为 ``[by_src | by_dst]``
#. ``apply_ip`` 是可选参数，其填写规则与 :ref:`ip_dm` 一致
#. ``track`` 和 ``apply_ip`` 必须一起使用，否则都不要使用
