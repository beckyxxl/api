# 创建文件系统-CreateUFSVolume

创建文件系统

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|Size|int|文件系统大小，单位为GB，最大不超过20T，香港容量型必须为100的整数倍，Size最小为500GB，北京，上海，广州的容量型必须为1024的整数倍，Size最小为1024GB。性能型文件系统Size最小为100GB|**Yes**|
|StorageType|string|文件系统存储类型，枚举值，Basic表示容量型，Advanced表示性能型|**Yes**|
|ProtocolType|string|文件系统协议，枚举值，NFSv3表示NFS V3协议，NFSv4表示NFS V4协议|**Yes**|
|VolumeName|string|文件系统名称|No|
|Remark|string|备注|No|
|Tag|string|文件系统所属业务组|No|
|ChargeType|string|计费模式，枚举值为： Year，按年付费； Month，按月付费； Dynamic，按需付费（需开启权限）； Trial，试用（需开启权限） 默认为Dynamic|No|
|Quantity|int|购买时长 默认: 1|No|
|CouponId|string|使用的代金券id|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|VolumeName|string|文件系统名称|**Yes**|
|VolumeId|string|文件系统ID|**Yes**|
|VolumeStatus|string|文件系统挂载点状态|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateUFSVolume
&VolumeName=saHszswLdzUZzUZsPiwCAnJtBouOgHSzIRb
&ProjectId=MIyyFdSR
&StorageType=Advanced
&ProtocolType=NFSv4
&Size=500
```

# Response Example
```
{
    "Action": "CreateUFSVolumeResponse", 
    "VolumeName": "zUZzUZsPiwCAnJ", 
    "VolumeStatus": "UnInitialized", 
    "VolumeId": "ufs-xxx", 
    "RetCode": 0
}
```

