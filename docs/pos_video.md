# 概述

> 目前我们已为第三方开发者提供``位置+视频``开放能力，帮助开发者快速获取设备基本信息、设备最新位置信息、设备历史轨迹、打开设备摄像头，实时查看设备视频画面、调取设备历史视频等能力。

---

## 用户登录

> 第三方开发者在调用各类开放能力时时，首先要通过开放平台的鉴权认证，为其分配有效的访问token后，才可授权调用其它能力接口

* 接口名称：``userlogin``

* 请求方式：``POST``

* 请求参数：

字段  | 类型 | 必填 | 说明
----| ---- | ---- | ---- 
mobile | string | true | 用户名(一般为注册手机号码) 
pwd | string | true | 登录密码(须MD5加密提交) 
logintype | int | true | 登录类型，缺省填0即可 
platform | string | false | 平台类型 
devicetoken | string | true | 设备识别号，接入IP等 
version | string | true | 应用版本号，如：``1.0.0.1``
packname | string | true | 包名 ``com.mapgoo.chedaibao``
flag | int | false | 是否返回所有设备自编号和流量卡号,1：不返回,0(缺省)：返回

* 返回参数：

字段  | 类型 | 说明
----| ---- | ---- 
authoken | string | 授权token，在请求以后的接口中需要填写到请求头的Authorization属性
userid | int | 用户ID 
username | string | 用户名称
objectid | Array | 该账号下所有设备自编号 
holdid | int | 用户渠道号 
holdname | string | 用户渠道名称 

* 请求示例：

```
curl http://192.168.100.96/v4/api/userlogin -X POST -d "
{
    "mobile": "test",
    "logintype": 0,
    "platform": "第三方",
    "packname":"com.mapgoo.chedaibao.mgkj",
    "pwd": "e10adc3949de59abbe543557f20f883e",
    "devicetoken":"",
    "version":"1.0.0",
    "flag": 1
}
"
```

## 设备信息

## 设备位置

## 设备轨迹

## 视频直播

## 历史视频

## 历史音频

## 消息下发