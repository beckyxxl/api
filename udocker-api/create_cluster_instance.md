# 创建集群-CreateClusterInstance

创建cluster实例

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|Zone|string|可用区。参见 [可用区列表](../summary/regionlist.html)|No|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ClusterName|string|Cluster集群名称|**Yes**|
|VPCId|string|VPCId|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ClusterId|string|返回新建的ClusterId|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=CreateClusterInstance
&Region=cn-bj2
&Zone=cn-bj2-04
&ProjectId=org-xxx
&ClusterName=cluster2
&VPCId=uvnet-xxx
```

# Response Example
```
{
    "Action": "CreateClusterInstanceResponse", 
    "ClusterId": "cluster-xxx", 
    "RetCode": 0
}
```

