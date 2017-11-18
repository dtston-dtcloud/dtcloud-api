# 简介
	深智云平台为企业应用提供用户管理、设备管理、数据统计等操作的接口，通讯方式采用HTTP，数据格式采用JSON。

### 1. 发送验证码
请求地址

<pre>POST	account/get_vcode</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|mobile|string|手机号|
|type|int|类型，1：注册、2：忘记密码|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 2. 登录
请求地址

<pre>POST	account/login</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|username|string|用户名，需要AES-256加密|
|assword|string|密码，需要AES-256加密|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 3. 登出
请求地址

<pre>POST	account/logout</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 4. 注册
请求地址

<pre>POST	account/register</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|username|string|用户名，需要AES-256加密|
|assword|string|密码，需要AES-256加密|
|repassword|string|确认密码，需要AES-256加密|
|vcode|string|验证码|
|fullname|string|姓名|
|enterprise_name|string|公司名称|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 5. 重置密码（忘记密码）
请求地址

<pre>POST	account/reset_pwd</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|username|string|用户名，需要AES-256加密|
|assword|string|密码，需要AES-256加密|
|repassword|string|确认密码，需要AES-256加密|
|vcode|string|验证码|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 6. 运营平台-用户管理-活跃用户-概览
请求地址

<pre>POST	statistics/active_user/overview</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 7. 运营平台-用户管理-活跃用户-数据趋势
请求地址

<pre>POST	statistics/active_user/trends</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|
|type|int|类型 1-过去7天、2-过去30天|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 8. 运营平台-告警管理-导出
请求地址

<pre>POST	alarm/export</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品ID|
|date|date|发生日期|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 9. 运营平台-告警管理-获取告警明细
请求地址

<pre>POST	alarm/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|age|int|页面，第1页开始|
|roduct_id|int|产品ID|
|date|date|发生日期|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 10. 运营平台-告警管理-概览
请求地址

<pre>POST	statistics/alarm/overview</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 11. 运营平台-告警管理-数据趋势
请求地址

<pre>POST	statistics/alarm/trends</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品ID|
|type|int|类型 1-过去7天、2-过去30天|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 12. 开发平台-产品开发-告警设置-删除告警规则
请求地址

<pre>POST	alert/del</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|alert_id|string|告警id|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 13. 开发平台-产品开发-告警设置-获取告警
请求地址

<pre>POST	alert/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品id|
|age|int|页面，第1页开始|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 14. 开发平台-产品开发-告警设置-添加告警规则
请求地址

<pre>POST	alert/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|alert_name|string|告警名称，最大20个字符|
|rotocol_id|string|协议id，协议的数据类型为字符串或数组时，start_index、end_index为必选|
|start_index|string|起始位置，不能大于end_index|
|end_index|string|结束位置，不能大于协议的字节数|
|alert_condition|string|告警条件 1-小于、2-等于、3-大于、4-小于等于、5-大于等于、6-不等于|
|alert_value|string|告警值|
|alert_content|string|告警内容，最大250个字符|
|alert_type|string|告警类型 1-设备异常、2-设备故障|
|notice_type|string|通知类型 1-通知型、2-告警型|
|notice_way|string|通知方式 1-极光推送|
|state|string|状态 0-禁用、1-启用|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 15. 开发平台-产品开发-告警设置-编辑告警规则
请求地址

<pre>POST	alert/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|alert_id|string|告警id|
|alert_name|string|告警名称，最大20个字符|
|rotocol_id|string|协议id，协议的数据类型为字符串或数组时，start_index、end_index为必选|
|start_index|string|起始位置，不能大于end_index|
|end_index|string|结束位置，不能大于协议的字节数|
|alert_condition|string|告警条件 1-小于、2-等于、3-大于、4-小于等于、5-大于等于、6-不等于|
|alert_value|string|告警值|
|alert_content|string|告警内容，最大250个字符|
|alert_type|string|告警类型 1-设备异常、2-设备故障|
|notice_type|string|通知类型 1-通知型、2-告警型|
|notice_way|string|通知方式 1-极光推送|
|state|string|状态 0-禁用、1-启用|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 16. 运营平台-APK升级-删除APK
请求地址

<pre>POST	apk/del</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|
|apk_id|int|APKID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 17. 运营平台-APK升级-获取APK
请求地址

<pre>POST	apk/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|age|int|页面，第1页开始|
|app_id|int|应用ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 18. 运营平台-APK升级-创建APK
请求地址

<pre>POST	apk/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|
|apk_name|string|APK名称，最大20个字符|
|reason|string|更新说明，最大255个字符|
|version|string|版本号，只允许是整数|
|file|string|APK文件地址|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 19. 获取所有应用
请求地址

<pre>POST	app/all_lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 20. 开发平台-产品开发-应用管理-删除应用
请求地址

<pre>POST	app/del</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用id|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 21. 开发平台-产品开发-应用管理-获取应用
请求地址

<pre>POST	app/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|age|int|页面，第1页开始|
|app_name|string|应用名称|
|type|string|类型，my-个人应用、dt-深智云应用|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 22. 开发平台-产品开发-应用管理-创建应用
请求地址

<pre>POST	app/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_name|string|应用名称，最大20个字符|
|type|string|应用分类 1-智能家居、2-智慧社区、3-智能硬件、4-智能健康、5-楼宇办公、6-智慧工业|
|image|string|应用图标|
|illustration|string|应用说明，最大250个字符|
|bundle_id|string|应用，最大50个字符|
|ackage_name|string|应用，最大50个字符|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 23. 开发平台-产品开发-应用管理-编辑应用
请求地址

<pre>POST	app/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用id|
|app_name|string|应用名称，最大20个字符|
|type|string|应用分类 1-智能家居、2-智慧社区、3-智能硬件、4-智能健康、5-楼宇办公、6-智慧工业|
|image|string|应用图标|
|illustration|string|应用说明，最大250个字符|
|bundle_id|string|应用，最大50个字符|
|ackage_name|string|应用，最大50个字符|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 24. 开发平台-产品开发-设备调试-删除设备
请求地址

<pre>POST	debug/del</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|string|应用ID|
|roduct_id|string|产品ID|
|id|string|数据ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 25. 开发平台-产品开发-设备调试-获取设备
请求地址

<pre>POST	debug/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|string|应用ID|
|roduct_id|string|产品ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 26. 开发平台-产品开发-设备调试-添加设备
请求地址

<pre>POST	debug/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|string|应用ID|
|roduct_id|string|产品ID|
|name|string|设备名称|
|mac|string|设备MAC|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 27. 开发平台-产品开发-设备调试-发送指令给设备
请求地址

<pre>POST	debug/send</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|mac|string|设备MAC地址|
|rotocol_id|string|协议ID|
|message_body|string|消息体|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 28. 运营平台-设备管理-设备授权-获取授权明细
请求地址

<pre>POST	device/auth_lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|age|int|页面，第1页开始|
|roduct_id|int|产品ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 29. 运营平台-设备管理-设备授权-概览
请求地址

<pre>POST	device/auth_overview</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 30. 运营平台-设备管理-设备情况-导出
请求地址

<pre>POST	device/export</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品ID|
|date|date|注册日期|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 31. 运营平台-设备管理-设备授权-导入
请求地址

<pre>POST	device/import</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品ID|
|data|string|MAC数据，多个MAC用逗号(,)分割，如（ACCF234F19B0）或者（ACCF234F19B0,ACCF2350A084）|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 32. 运营平台-设备管理-设备情况-获取设备明细
请求地址

<pre>POST	device/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|age|int|页面，第1页开始|
|roduct_id|int|产品ID|
|date|date|注册日期|
|state|string|状态 0-全部、1-离线、2-在线|
|is_bind|string|绑定用户 0-全部、1-未绑定、2-已绑定|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 33. 运营平台-设备管理-设备情况-概览
请求地址

<pre>POST	statistics/device/overview</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 34. 运营平台-设备管理-设备情况-数据趋势
请求地址

<pre>POST	statistics/device/trends</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品ID|
|type|int|类型 1-过去7天、2-过去30天|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 35. 运营平台-首页-设备分布
请求地址

<pre>POST	statistics/enterprise/device_distributed</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 36. 运营平台-首页-设备趋势
请求地址

<pre>POST	statistics/enterprise/device_trends</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|type|string|类型 1-过去7天、2-过去30天|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 37. 获取企业信息
请求地址

<pre>POST	enterprise/info</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 38. 运营平台-首页-概览
请求地址

<pre>POST	statistics/enterprise/overview</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 39. 编辑企业信息
请求地址

<pre>POST	enterprise/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|enterprise_name|string|企业名称|
|type|string|类型 1-互联网、2-工业、3-农业、4-医疗、5-物联网、6-家居|
|contact|string|联系人|
|contact_number|string|联系电话|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 40. 运营平台-首页-用户分布
请求地址

<pre>POST	statistics/enterprise/user_distributed</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 41. 运营平台-首页-用户机型分布
请求地址

<pre>POST	statistics/enterprise/user_model_distributed</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 42. 运营平台-首页-用户趋势
请求地址

<pre>POST	statistics/enterprise/user_trends</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|type|string|类型 1-过去7天、2-过去30天|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 43. 运营平台-常见问题管理-删除常见问题
请求地址

<pre>POST	faq/del</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|faq_id|string|常见问题ID|
|app_id|string|应用ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 44. 运营平台-常见问题管理-获取常见问题
请求地址

<pre>POST	faq/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|age|int|页面，第1页开始|
|app_id|int|应用ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 45. 运营平台-常见问题管理-新增常见问题
请求地址

<pre>POST	faq/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|string|应用ID|
|type|string|类型 1-常见问题、2-基础知识|
|question|string|问题、最大50个字符|
|answer|string|答案|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 46. 运营平台-常见问题管理-编辑常见问题
请求地址

<pre>POST	faq/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|faq_id|string|常见问题ID|
|app_id|string|应用ID|
|type|string|类型 1-常见问题、2-基础知识|
|question|string|问题、最大50个字符|
|answer|string|答案|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 47. 运营平台-用户反馈-删除
请求地址

<pre>POST	feedback/del</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|
|id|string|要删除的反馈ID，用逗号(,)拼接的字符串，如：(1)或者(1,2,3)|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 48. 运营平台-用户反馈-获取反馈列表
请求地址

<pre>POST	feedback/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|age|int|页面，第1页开始|
|app_id|int|应用ID|
|status|int|状态 0-全部、1-未读、2-已读|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 49. 运营平台-用户反馈-修改状态
请求地址

<pre>POST	feedback/status</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|
|feedback_id|string|反馈ID|
|status|string|状态 0-未读、1-已读|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 50. 运营平台-固件升级-删除固件
请求地址

<pre>POST	firmware/del</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品ID|
|firmware_id|int|固件ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 51. 运营平台-固件升级-获取固件
请求地址

<pre>POST	firmware/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|age|int|页面，第1页开始|
|roduct_id|int|产品ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 52. 运营平台-固件升级-创建固件
请求地址

<pre>POST	firmware/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品ID|
|name|string|固件名称，最大20个字符|
|version|string|固件版本，只允许是整数|
|file|string|固件文件地址|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 53. 运营平台-邮件模板-获取模板
请求地址

<pre>POST	mail_template/info</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 54. 运营平台-邮件模板-保存模板
请求地址

<pre>POST	mail_template/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|
|type|string|类型 1-邮箱验证码模板、2-密码找回模板|
|title|string|标题|
|content|string|内容|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 55. 获取个人信息
请求地址

<pre>POST	member/info</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 56. 编辑个人信息
请求地址

<pre>POST	member/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|fullname|string|姓名，最大20个字符|
|image|string|头像地址|
|old_pwd|string|旧密码|
|new_pwd|string|新密码|
|repwd|string|确认密码|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 57. 运营平台-消息推送-新增消息
请求地址

<pre>POST	msg/add</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|
|title|string|标题，最大20个字符|
|content|string|内容，最大100个字符|
|way|string|推送方式 1-极光|
|crowd|string|推送人群 1-群发、2-单发|
|mobile|string|单发的时候填写的手机号|
|url|string|链接地址|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 58. 运营平台-消息推送-获取配置
请求地址

<pre>POST	msg/info</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 59. 运营平台-消息推送-获取消息
请求地址

<pre>POST	msg/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|age|int|页面，第1页开始|
|app_id|int|应用ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 60. 运营平台-消息推送-保存配置
请求地址

<pre>POST	msg/save_info</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|
|app_key|string||
|app_secret|string||
|env|string|环境 0-开发环境、1-生产环境|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 61. 获取所有产品
请求地址

<pre>POST	roduct/all_lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|String|应用ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 62. 开发平台-产品开发-产品管理-删除产品
请求地址

<pre>POST	roduct/del</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品id|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 63. 开发平台-产品开发-产品管理-获取产品
请求地址

<pre>POST	roduct/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用id，0为所有应用|
|age|int|页面，第1页开始|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 64. 开发平台-产品开发-产品管理-创建产品
请求地址

<pre>POST	roduct/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_name|string|产品名称，最大20个字符|
|app_id|string|应用id|
|category|string|设备类别 1-安防硬件、2-办公设备、3-宠物看护、4-健康养生、5-开发调试用硬件、6-社区公共设施、7-智能穿戴、8-智能家电、9-其他|
|module|string|WiFi模块 1-汉枫LPB100、2-汉枫LPT100、3-汉枫LPT200、4-汉枫LPB120、5-汉枫LPT120、6-乐鑫WT8266-S1、7-庆科3081、8-瑞昱RTL8710、9-LPB125、10-LPT220、11-南方硅谷SSV6060|
|lan|string|技术方案 1-WiFi|
|image|string|图片|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 65. 开发平台-产品开发-产品管理-编辑产品
请求地址

<pre>POST	roduct/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品id|
|roduct_name|string|产品名称，最大20个字符|
|app_id|string|应用id|
|category|string|设备类别 1-安防硬件、2-办公设备、3-宠物看护、4-健康养生、5-开发调试用硬件、6-社区公共设施、7-智能穿戴、8-智能家电、9-其他|
|module|string|WiFi模块 1-汉枫LPB100、2-汉枫LPT100、3-汉枫LPT200、4-汉枫LPB120、5-汉枫LPT120、6-乐鑫WT8266-S1、7-庆科3081、8-瑞昱RTL8710、9-LPB125、10-LPT220、11-南方硅谷SSV6060|
|lan|string|技术方案 1-WiFi|
|image|string|图片|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 66. 开发平台-产品开发-协议管理-查看协议
请求地址

<pre>POST	rotocol/all_lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品id|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 67. 开发平台-产品开发-协议管理-删除协议
请求地址

<pre>POST	rotocol/del</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|rotocol_id|int|协议id|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 68. 获取所有下发协议
请求地址

<pre>POST	rotocol/downlists</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 69. 开发平台-产品开发-协议管理-下载协议
请求地址

<pre>POST	rotocol/download</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品id|
|type|int|下载类型 1-嵌入式开发协议、2-APP应用开发协议|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 70. 开发平台-产品开发-协议管理-获取协议
请求地址

<pre>POST	rotocol/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品id|
|age|int|页面，第1页开始|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 71. 开发平台-产品开发-协议管理-添加协议
请求地址

<pre>POST	rotocol/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|int|产品id|
|rotocol_name|string|协议名称，最大20个字符|
|rotocol_type|string|协议类型 1-双向、2-下发、3-上报，1或2时（down_code、down_data_type、down_bytes必选），1或3时（up_code、up_data_type、up_bytes必选）|
|down_code|string|下发功能码，格式为10xx，16进制字符串|
|down_data_type|string|下发数据类型 1-布尔类型（1个字节）、2-单字节（有符号）、3-单字节（无符号）、4-16位短整型（有符号）、5-16位短整型（无符号）、6-32位整型（有符号）、7-32位整型（无符号）、8-浮点、9-字符串、10-字节数组|
|down_bytes|string|下发字节数，down_data_type为8或9时可填充，否则默认填充，最大值60000|
|down_unit|string|下发单位符合|
|down_desc|string|下发描述|
|up_code|string|上报功能码，格式为18xx，16进制字符串|
|up_data_type|string|上报数据类型 1-布尔类型（1个字节）、2-单字节（有符号）、3-单字节（无符号）、4-16位短整型（有符号）、5-16位短整型（无符号）、6-32位整型（有符号）、7-32位整型（无符号）、8-浮点、9-字符串、10-字节数组|
|up_bytes|string|上报字节数，up_data_type为8或9时可填充，否则默认填充，最大值60000|
|up_unit|string|上报单位符合|
|up_desc|string|上报描述|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 72. 开发平台-产品开发-协议管理-编辑协议
请求地址

<pre>POST	rotocol/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|rotocol_id|int|协议id|
|roduct_id|int|产品id|
|rotocol_name|string|协议名称，最大20个字符|
|rotocol_type|string|协议类型 1-双向、2-下发、3-上报，1或2时（down_code、down_data_type、down_bytes必选），1或3时（up_code、up_data_type、up_bytes必选）|
|down_code|string|下发功能码，格式为10xx，16进制字符串|
|down_data_type|string|下发数据类型 1-布尔类型（1个字节）、2-单字节（有符号）、3-单字节（无符号）、4-16位短整型（有符号）、5-16位短整型（无符号）、6-32位整型（有符号）、7-32位整型（无符号）、8-浮点、9-字符串、10-字节数组|
|down_bytes|string|下发字节数，down_data_type为8或9时可填充，否则默认填充，最大值60000|
|down_unit|string|下发单位符合|
|down_desc|string|下发描述|
|up_code|string|上报功能码，格式为18xx，16进制字符串|
|up_data_type|string|上报数据类型 1-布尔类型（1个字节）、2-单字节（有符号）、3-单字节（无符号）、4-16位短整型（有符号）、5-16位短整型（无符号）、6-32位整型（有符号）、7-32位整型（无符号）、8-浮点、9-字符串、10-字节数组|
|up_bytes|string|上报字节数，up_data_type为8或9时可填充，否则默认填充，最大值60000|
|up_unit|string|上报单位符合|
|up_desc|string|上报描述|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 73. 获取所有上报协议
请求地址

<pre>POST	rotocol/uplists</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 74. 开发平台-数据转发-申请
请求地址

<pre>POST	transfer/apply</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 75. 开发平台-数据转发-删除转发
请求地址

<pre>POST	transfer/del</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|transfer_id|string|转发ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 76. 开发平台-数据转发-获取转发
请求地址

<pre>POST	transfer/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|age|int|页面，第1页开始|
|roduct_id|int|产品ID，0-所有产品|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 77. 开发平台-数据转发-添加转发
请求地址

<pre>POST	transfer/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|roduct_id|string|产品ID|
|transfer_rule|string|转发规则 1-设备上线、2-设备下线、3-数据变化（多选用逗号,分隔，如1,2,3）|
|transfer_type|string|转发类型 1-外部URL|
|transfer_url|string|转发URL|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 78. 开发平台-数据转发-编辑转发
请求地址

<pre>POST	transfer/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|transfer_id|string|转发ID|
|roduct_id|string|产品ID|
|transfer_rule|string|转发规则 1-设备上线、2-设备下线、3-数据变化（多选用逗号,分隔，如1,2,3）|
|transfer_type|string|转发类型 1-外部URL|
|transfer_url|string|转发URL|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 79. 文件上传
请求地址

<pre>POST	upload/upload_file</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|file|stream|图片资源|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 80. 图片上传
请求地址

<pre>POST	upload/upload_img</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|file|stream|图片资源|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 81. 运营平台-用户管理-用户情况-导出
请求地址

<pre>POST	user/export</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|
|date|date|注册日期|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 82. 运营平台-用户管理-用户情况-获取用户明细
请求地址

<pre>POST	user/lists</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|age|int|页面，第1页开始|
|app_id|int|应用ID|
|date|date|注册日期|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 83. 运营平台-用户管理-用户情况-概览
请求地址

<pre>POST	statistics/user/overview</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 84. 运营平台-用户管理-用户情况-数据趋势
请求地址

<pre>POST	statistics/user/trends</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_id|int|应用ID|
|type|int|类型 1-过去7天、2-过去30天|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 85. 开发平台-智能互联-萤石摄像头-获取信息
请求地址

<pre>POST	yingshi/info</pre>

请求参数

|字段|类型|描述|
|--|--|--|

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
### 86. 开发平台-智能互联-萤石摄像头-编辑信息
请求地址

<pre>POST	yingshi/save</pre>

请求参数

|字段|类型|描述|
|--|--|--|
|app_key|string||
|app_secret|string||

返回参数

|字段|类型|描述|
|--|--|--|
|errcode|int|返回码，返回0是成功，其余都是错误|
|errmsg|string|错误信息，可以直接显示给用户|
