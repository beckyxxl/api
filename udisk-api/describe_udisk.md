# 获取云硬盘列表-DescribeUDisk

获取UDisk实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|UDiskId|string|UDisk Id(留空返回全部)|No|
|Offset|int|数据偏移量, 默认为0|No|
|Limit|int|返回数据长度, 默认为20|No|
|DiskType|string|ProtocolVersion字段为1时，需结合IsBoot确定具体磁盘类型:普通数据盘：DiskType:"CLOUD_NORMAL",IsBoot:"False"； 普通系统盘：DiskType:"CLOUD_NORMAL",IsBoot:"True"；SSD数据盘：DiskType:"CLOUD_SSD",IsBoot:"False"；SSD系统盘：DiskType:"CLOUD_SSD",IsBoot:"True"；RSSD数据盘：DiskType:"CLOUD_RSSD",IsBoot:"False"；为空拉取所有。ProtocolVersion字段为0或没有该字段时，可设为以下几个值:普通数据盘：DataDisk；普通系统盘：SystemDisk；SSD数据盘：SSDDataDisk；SSD系统盘：SSDSystemDisk；RSSD数据盘：RSSDDataDisk；为空拉取所有。|No|
|ProtocolVersion|int|请求协议版本，建议升级为1，为1时DiskType与UHost磁盘类型定义一致；默认为0|No|
|IsBoot|string|ProtocolVersion字段为1且DiskType不为空时，必须设置，设置规则请参照DiskType；ProtocolVersion字段为1且DiskType为空时，该字段无效。ProtocolVersion字段为0或没有该字段时，该字段无效。|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|DataSet|array|JSON 格式的UDisk数据列表, 每项参数可见下面 UDiskDataSet|No|
|TotalCount|int|根据过滤条件得到的总数|No|

## UDiskDataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|可用区|No|
|UDiskId|string|UDisk实例Id|No|
|Name|string|实例名称|No|
|Size|int|容量单位GB|No|
|Status|string|状态:Available(可用),Attaching(挂载中), InUse(已挂载), Detaching(卸载中), Initializating(分配中), Failed(创建失败),Cloning(克隆中),Restoring(恢复中),RestoreFailed(恢复失败),|No|
|CreateTime|int|创建时间|No|
|ExpiredTime|int|过期时间|No|
|UHostId|string|挂载的UHost的Id|No|
|UHostName|string|挂载的UHost的Name|No|
|UHostIP|string|挂载的UHost的IP|No|
|DeviceName|string|挂载的设备名称|No|
|ChargeType|string|Year,Month,Dynamic,Trial,Postpay|No|
|Tag|string|业务组名称|No|
|IsExpire|string|资源是否过期，过期:"Yes", 未过期:"No"|No|
|Version|string|是否支持数据方舟，支持:"2.0", 不支持:"1.0"|No|
|UDataArkMode|string|是否开启数据方舟，开启:"Yes", 不支持:"No"|No|
|SnapshotCount|int|该盘快照个数|No|
|SnapshotLimit|int|该盘快照上限|No|
|DiskType|string|请求中的ProtocolVersion字段为1时，需结合IsBoot确定具体磁盘类型:普通数据盘：DiskType:"CLOUD_NORMAL",IsBoot:"False"； 普通系统盘：DiskType:"CLOUD_NORMAL",IsBoot:"True"；SSD数据盘：DiskType:"CLOUD_SSD",IsBoot:"False"；SSD系统盘：DiskType:"CLOUD_SSD",IsBoot:"True"；RSSD数据盘：DiskType:"CLOUD_RSSD",IsBoot:"False"。请求中的ProtocolVersion字段为0或没有该字段时，云硬盘类型参照如下:普通数据盘：DataDisk；普通系统盘：SystemDisk；SSD数据盘：SSDDataDisk；SSD系统盘：SSDSystemDisk；RSSD数据盘：RSSDDataDisk。|No|
|CloneEnable|int|是否支持克隆，1支持 ，0不支持|No|
|SnapEnable|int|是否支持快照，1支持 ，0不支持|No|
|ArkSwitchEnable|int|是否支持开启方舟，1支持 ，0不支持|No|
|UKmsMode|string|是否是加密盘，是:"Yes", 否:"No"|No|
|CmkId|string|该盘的cmk id|No|
|DataKey|string|该盘的密文密钥|No|
|CmkIdStatus|string|该盘cmk的状态, Enabled(正常)，Disabled(失效)，Deleted(删除)，NoCmkId(非加密盘)|No|
|CmkIdAlias|string|cmk id 别名|No|
|IsBoot|string|是否是系统盘，是："True", 否："False"|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeUDisk
&Region=cn-bj2-02
&UDiskId=bs-xxx
&Offset=0
&Limit=20
&ProtocolVersion=8
&IsBoot=irVoOnAn
```

# Response Example
```
{
    "Action": "DescribeUDiskResponse", 
    "TotalCount": 50, 
    "RetCode": 0, 
    "DataSet": [
        {
            "Status": "Cloning", 
            "DeviceName": "", 
            "UHostId": "", 
            "Version": "2.0", 
            "Name": "udisk_uda_1", 
            "Zone": "cn-bj2-02", 
            "UHostIP": "", 
            "CreateTime": 1492529621, 
            "DiskType": "DataDisk", 
            "SnapshotLimit": 3, 
            "UHostName": "", 
            "Tag": "Default", 
            "SnapshotCount": 0, 
            "IsExpire": "No", 
            "UDataArkMode": "No", 
            "UDiskId": "bs-xxx", 
            "ExpiredTime": 1509706800, 
            "ChargeType": "Dynamic", 
            "Size": 10
        }
    ]
}
```

