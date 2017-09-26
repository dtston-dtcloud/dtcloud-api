# 简介
深智云平台为设备提供设备激活、设备认证等操作的接口

协议方式：TCP、短链接

数据传输格式：JSON

接口流程:

	先调用设备激活，激活成功再调用设备认证。
	
## 接口列表	

[1. 设备激活](#device_activation)

[2. 设备认证](#device_verify)

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


