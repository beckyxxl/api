# 删除令牌-DeleteUFileToken

删除令牌

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|**Yes**|
|TokenId|string|令牌ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|

# Request Example
```
https://api.ucloud.cn/?Action=DeleteUFileToken
&ProjectId=org-mutvtj
&Region=cn-bj
&TokenId=679c7e5e-74b8-4048-b622-33dd4e8634db
```

# Response Example
```
{
    "Action": "DeleteUFileTokenResponse", 
    "RetCode": 0
}
```

