# 启动物理机-StartPHost

启动物理机

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|PHostId|string|PHost资源ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|PHostId|string|PHost 的资源ID|No|

# Request Example
```
https://api.ucloud.cn/?Action=StartPHost
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&PHostId=upm-xxx
```

# Response Example
```
{
    "Action": "StartPHostResponse", 
    "PHostId": "upm-xxx", 
    "RetCode": 0
}
```

