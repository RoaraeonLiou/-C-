# 预处理文件编写

```ymal
parsers: # array
	- url: 订阅URL地址
	  yaml:
	  	mix-proxy-providers: 	# 对象合并至原配置proxy-providers中
	  	mix-rule-providers: 	# 对象合并至原配置rule-providers中
	  	prepend-proxies: 		# 头部插入策略
	  		- 添加的策略
	  	append-proxies: 		# 尾部插入策略
	  		- 添加的策略
	  	prepend-proxy-groups: 	# 头部插入策略组
	  		- 追加的策略组
	  	append-proxy-groups: 	# 尾部插入策略组
	  		- 追加的策略组
   		prepend-rules: 			# 头部插入规则
   			- 插入的规则
   		append-rules: 			# 尾部插入规则
   			- 插入的规则
```

编写好预处理文件后，更新订阅时，会按需要新增的内容与订阅文件融合。

由于规则由上至下匹配，所以推荐将自定义规则采用prepend方式插入。