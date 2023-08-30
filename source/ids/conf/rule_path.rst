RulePath
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
 
在``RulePath``填写规则文件地址或存放规则文件的目录，例：

.. code:: json

 {
   "RulePath":[
     "/etc/rules/test/rule_1.rules",
	 "/etc/rules/main"
   ]
 }
 
当给出的规则文件的绝对路径时，文件的后缀可以不是 ``.rules``

当给出的是目录，那么该目录中的规则文件的后缀必须是 ``.rules``，否则将不会被读取

END