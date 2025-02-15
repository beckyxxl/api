# 创建VServer-CreateVServer

创建VServer实例，定义监听的协议和端口以及负载均衡算法

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|ULBId|string|负载均衡实例ID|**Yes**|
|VServerName|string|VServer实例名称，默认为"VServer"|No|
|ListenType|string|监听器类型，枚举值为：RequestProxy -> 请求代理；PacketsTransmit -> 报文转发；默认为"RequestProxy"|No|
|Protocol|string|VServer实例的协议，请求代理模式下有 HTTP、HTTPS、TCP，报文转发下有 TCP，UDP。默认为“HTTP"|No|
|FrontendPort|int|VServer后端端口，取值范围[1-65535]；默认值为80|No|
|Method|string|VServer负载均衡模式，枚举值：Roundrobin -> 轮询;Source -> 源地址；ConsistentHash -> 一致性哈希；SourcePort -> 源地址（计算端口）；ConsistentHashPort -> 一致性哈希（计算端口）; WeightRoundrobin -> 加权轮询; Leastconn -> 最小连接数。ConsistentHash，SourcePort，ConsistentHashPort 只在报文转发中使用；Leastconn只在请求代理中使用；Roundrobin、Source和WeightRoundrobin在请求代理和报文转发中使用。默认为："Roundrobin"|No|
|PersistenceType|string|VServer会话保持方式，默认关闭会话保持。枚举值：None -> 关闭；ServerInsert -> 自动生成KEY；UserDefined -> 用户自定义KEY。|No|
|PersistenceInfo|string|根据PersistenceType确认； None和ServerInsert： 此字段无意义； UserDefined：此字段传入自定义会话保持String|No|
|ClientTimeout|int|ListenType为RequestProxy时表示空闲连接的回收时间，单位：秒，取值范围：时(0，86400]，默认值为60；ListenType为PacketsTransmit时表示连接保持的时间，单位：秒，取值范围：[60，900]，0 表示禁用连接保持|No|
|MonitorType|string|健康检查类型，枚举值：Port -> 端口检查；Path -> 路径检查；|No|
|Domain|string|根据MonitorType确认； 当MonitorType为Port时，此字段无意义。当MonitorType为Path时，代表HTTP检查域名|No|
|Path|string|根据MonitorType确认； 当MonitorType为Port时，此字段无意义。当MonitorType为Path时，代表HTTP检查路径|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|VServerId|string|VServer实例的Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateVServer
&Region=cn-bj2
&ProjectId=project-XXXXX
&Action=CreateVServer
&ULBId=ulb-XXXXX
&ListenType=RequestProxy
&PersistenceType=None
&PersistenceInfo=hsdhs
&Protocol=TCP
&VServerName=testvserver1
&Method=Source
&FrontendPort=80
&ClientTimeout=180
&MonitorType=EAWmpFKo
&Domain=HbTPGDtS
&Path=ScoEPSuy
```

# Response Example
```
{
    "Action": "CreateVServerResponse", 
    "VServerId": "vserver-XXXX", 
    "RetCode": 0
}
```

