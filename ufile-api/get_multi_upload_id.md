# 获取正在执行的分片上传id-GetMultiUploadId

获取正在执行的分片上传id

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Prefix|string|前缀，utf-8编码，默认为空字符串|No|
|Marker|string|标志字符串，utf-8编码，默认为空字符串|No|
|Limit|int|id列表数目，默认为20|No|

```
Syntax:
	GET /?muploadid&prefix=<prefix>&marker=<marker>&limit=<limit>
	Host: <bucket_name>.ufile.ucloud.cn
	Authorization: <token> 

Request Headers
	Authorization 下载请求的授权签名
```

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ErrMsg|string|错误提示|No|
|NextMarker|string|下一个标志字符串，utf-8编码|No|
|DataSet|array|上传id列表|No|

## DataSet
|Parameter name|Type|Description|Required|
|---|---|---|---|
|CPUUtilization|array|cpu使用率|No|
|MemUtilization|array|内存使用率|No|
|NICOut|array|网卡出带宽|No|
|NICIn|array|网卡入带宽|No|
|NetPacketOut|array|网卡出包量|No|
|NetPacketIn|array|网卡入包量|No|
|IORead|array|磁盘读取量|No|
|IOWrite|array|磁盘写入量|No|
|DiskReadOps|array|磁盘读取次数|No|
|DiskWriteOps|array|磁盘写入次数|No|

## MonitorInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|TimeStamp|int|时间戳|**Yes**|
|Value|int|值|**Yes**|

# Request Example
```
GET /?muploadid&prefix=lar&marker=a&limit=20 HTTP/1.1
Host: example.cn-bj.ufileos.ucloud.cn
Authorization:UCloud pRAtiCbYdYI9wqHMqcQe0D9m16YpTsKBVL3GeBZ6wn6N+00uMrI7NQ==:VdDRXKoBjX6FnxjOz+HbLtswW50=
```

# Response Example
```
{
    "NextMarker": "", 
    "RetCode": 0, 
    "ErrMsg": "", 
    "DataSet": [
        {
            "UploadId": "3be8bd2b-4188-41d5-ac80-9ddf644a090c", 
            "StartTime": 1484116878, 
            "FileName": "large_file_version_2"
        }, 
        {
            "UploadId": "e5af977e-329c-4a25-b907-d8bc39ff95e3", 
            "StartTime": 1484117647, 
            "FileName": "large_file_version_4"
        }
    ]
}
```

