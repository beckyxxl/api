# 创建单机Memcache-CreateUMemcacheGroup

创建单机Memcache

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Name|string|请求创建组的名称 范围[6-60]|**Yes**|
|Size|int|每个节点的内存大小,单位GB,默认1GB 目前仅支持1/2/4/8/16/32这几档|No|
|ConfigId|string|配置ID,目前仅支持默认配置id 默认配置id:"9a891891-c245-4b66-bce8-67e59430d67c"|No|
|Version|string|Memcache版本信息,默认为1.4.31|No|
|ChargeType|string|计费模式，Year , Month, Dynamic 默认: Month|No|
|Quantity|int|购买时长，默认为1|No|
|Tag|string|业务组 默认：Default|No|
|Protocol|string||No|
|CouponId|string|代金券ID|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|GroupId|string|创建的组ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUMemcacheGroup
&Region=cn-bj2
&Zone=cn-bj2-04
&Name=djdj_XXXXX
&SubnetId=qVnAwdPw
&Protocol=fmwGhgdR
```

# Response Example
```
{
    "Action": "CreateUMemcacheGroupResponse", 
    "RetCode": 0, 
    "GroupId": "00f9868c-c7f5-4852-9eac-d200b678f0e1"
}
```

