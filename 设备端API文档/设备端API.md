# 简介
	深智云平台为设备提供设备激活、设备认证等操作的接口，通讯方式采用TCP短链接，数据格式采用JSON。

设备接入流程:

	先调用设备激活接口，完成激活操作。激活成功后再调用设备认证接口，完成认证操作。
	
## 接口列表	

[1. 设备激活](#device_activation)

[2. 设备认证](#device_verify)
<style>table th {width: 200px;}</style>
| 水果| 价格|数量|
|--|:--:|:--:|
| 香蕉|$1|5|
| 苹果|$1|6|
| 草莓|$1|7|

## 接口详情
### <a name="device_activation">1. 设备激活</a>
请求内容

    {
        "func":"activation"
        "device_identifier":"设备唯一标识，如设备MAC地址",
        "device_type":"设备类型"
    }

响应内容

    {
        "code":错误码，0表示成功，非0表示错误,
        "msg":"错误内容"
    }
    或
    {
        "code":错误码，0表示成功，非0表示错误,
        "msg":"错误内容",
        "did":"设备ID"
    }

### <a name="device_verify">2. 设备认证</a>
请求内容

    {
        "func":"verify"
        "device_identifier":"设备唯一标识，如设备MAC地址",
        "device_type":"设备类型",
        "did":"设备ID"
    }

响应内容

    {
        "code":错误码，0表示成功，非0表示错误,
        "msg":"错误内容"
    }


