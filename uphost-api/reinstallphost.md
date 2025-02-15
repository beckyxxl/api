# 重装物理机-ReinstallPHost

重装物理机操作系统

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|PHostId|string|PHost资源ID|**Yes**|
|Password|string|密码|**Yes**|
|ImageId|string|镜像Id，参考镜像列表，默认使用原镜像|No|
|Name|string|物理机名称，默认不更改|No|
|Remark|string|物理机备注，默认为不更改。|No|
|Tag|string|业务组，默认不更改。|No|
|ReserveDisk|string|是否保留数据盘，保留：Yes，不报留：No， 默认：Yes|No|
|Raid|string|不保留数据盘重装，可选Raid|No|

```
密码需要通过base64进行编码

# echo password1 | base
ugfzc3dvcmqxcg==
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PHostId|string|PHost 的资源ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=ReinstallPHost
&Region=cn-bj2
&Zone=cn-bj2-04
&Password=123
&Hostname=123
&ImageId=pimg-yg-f2634b
&SaveDataDisk=Yes
&PHostId=upm-oaix4s&ProjectId=org1
```

# Response Example
```
{
    "Action": "ReinstallPHostResponse", 
    "PHostId": "upm-oaix4s", 
    "RetCode": 0
}
```

