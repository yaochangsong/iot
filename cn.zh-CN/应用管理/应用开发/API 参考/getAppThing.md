# getAppThing {#reference_ljp_lfs_qfb .reference}

调用该接口获取物（设备）的基本信息。

## 请求路径 {#section_kk5_x4t_qfb .section}

该接口的请求路径：/app/thing/info/get

## 请求参数 {#section_rbv_cpt_qfb .section}

|参数|类型|是否必需|描述|
|:-|:-|:---|:-|
|基础参数|-|是|调用应用管理API所需基础参数，请参见[基础参数](cn.zh-CN/应用管理/应用开发/API 参考/基础参数.md#)。|
|iotId|String|否|设备ID，设备的唯一标识。**说明：** 如果传入该参数，则无需传入productKey和deviceName。iotId作为设备唯一标识符，和productKey与DeviceName组合是一一对应的关系。如果您同时传入iotId和productKey与deviceName组合，则以iotId为准。

|
|productKey|String|否|设备所隶属的产品Key。**说明：** 如果传入该参数，需同时传入deviceName。

|
|deviceName|String|否|设备名称。**说明：** 如果传入该参数，需同时传入productKey。

|

## 返回参数 {#section_cl2_rst_qfb .section}

|参数|类型|描述|
|:-|:-|:-|
|id|String|物联网平台为该请求生成的唯一标识符。|
|code|Integer|返回的结果状态码。-   调用成功，则返回码为 200。
-   若调用失败，则返回具体错误码。错误码详情参见[通用错误码](cn.zh-CN/应用管理/应用开发/API 参考/通用错误码.md#)。

|
|message|String|调用结果的英文描述。-   当返回的code为200时，message为success。
-   当返回的code为其他错误码时，message为该错误码对应的具体描述。具体信息，请参见[通用错误码](cn.zh-CN/应用管理/应用开发/API 参考/通用错误码.md#)。

|
|localizedMsg|String|本地化语言的调用结果描述，目前为空。|
|data|Object|调用成功时，返回的数据。详情参见下表 data。|

|名称|类型|描述|
|:-|:-|:-|
|productKey|String|设备所隶属的产品 Key。|
|name|String|设备名称。|
|nickname|String|设备昵称。|
|deviceSecret|String|设备密钥。|
|deviceKey|String|设备 Key。|
|iotId|String|设备 ID。物联网平台为设备颁发的 ID，作为该设备的唯一标识符。|
|thingType|String|设备类型，取值：-   VIRTUAL：虚拟设备。
-   DEVICE：真实设备。

|
|region|String|设备所在地域（与物联网地平台控制台上的服务地域对应）。|
|gmtCreate|Long|设备的创建时间。|
|gmtModified|Long|设备数据修改时间。|
|activeTime|Long|设备激活时间。|
|sdkVersion|String|设备的 SDK 版本号。|
|firmwareVersion|String|设备的固件版本号。|
|mac|String|设备的 MAC 地址。|
|status|Integer|设备状态。取值：-   0：未激活。
-   1：在线。
-   3：离线。
-   8：已禁用。

|
|statusLast|Integer|设备的上一个状态。|
|rbacTenantId|String|租户 ID。|
|netAddress|String|设备网络地址。|

## 示例 {#section_qs1_zxt_qfb .section}

**请求示例**

```
{
    "id": "bded4128dc454a03b3d10c45de17b863",
    "version": "1.0",
    "request": {
        "apiVer": "1.0.0"
    },
    "params": {
        "iotId": "D95D242941CE821ECCE4F31A2697"
    }
}
```

**返回示例**

```
{
    "id":"bded4128-dc45-4a03-b3d1-0c45de17b863",    
    "code":200,
    "data":{
        "gmtModified":1517918765000,
        "activeTime":null,
        "deviceKey":"Kq7rgvE2cNGcwtDexwJh",
        "gmtCreate":1500017648000,
        "productKey":"kQGJJuTl0qA",
        "statusLast":null,
        "mac":null,
        "netAddress":null,
        "deviceSecret":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "iotId":"03iGXYVl03e23f667d90269c2ccwgzHG",
        "name":"Kq7rgvE2cNGcwtDexwJh",
        "nickname":null,
        "sdkVersion":null,
        "thingType":"DEVICE",
        "region":"daily",
        "firmwareVersion":"1.0.0",
        "rbacTenantId":"ADSBCUYAGDCUDD827918327917",
        "status":1
    },
    "message":"success",
    "localizedMsg":null
}
```

