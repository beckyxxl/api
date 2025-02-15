# 获取截图任务详情-GetSnapTaskDetail

获取截图任务详情

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](../summary/get_project_list.html)|No|
|TaskId|string|查询的截图任务ID|**Yes**|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|SrcUrl|string|原始视频url地址|No|
|SnapType|string|截图模式，single表示确定时间点单张截图，periodic表示周期截图,dynamic表示为gif截图|No|
|ImageName|string|截图输出的文件名（这里指基础图片的文件名，不包括后缀）|No|
|ImageFormat|string|图片格式类型|No|
|ImageCount|int|截图张数，只有任务状态处理完成时值才有意义。|No|
|DestBucket|string|存储图片的ufile的bucket名称|No|
|CreateTime|int|任务创建时间，单位：Unix时间戳|No|
|FinishTime|int|任务结束时间，单位：Unix时间戳。只有任务状态为处理完成时值才有意义，默认为0。|No|
|Status|string|任务状态：waiting、processing、finished、failed，分别表示排队中，处理中，处理完成，处理失败。|No|
|ImageList|string|文件名列表|No|

# Request Example
```
https://api.ucloud.cn/?Action=GetSnapTaskDetail&TaskId=1
```

# Response Example
```
{
    "FinishTime": 1496298900, 
    "Status": "finished", 
    "DestBucket": "video.cn-bj.ufileos.com", 
    "RetCode": 0, 
    "SrcUrl": "http://video.ucloud.cn/myvideo.mp4", 
    "ImageFormat ": "jpg", 
    "ImageName": "myvideo.jpg", 
    "TaskId": "1", 
    "Action": "GetSnapTaskDetailResponse", 
    "ImageList": [
        "myvideo_0.jpg", 
        "myvideo_1.jpg", 
        "myvideo_2.jpg", 
        "myvideo_3.jpg", 
        "myvideo_4.jpg"
    ], 
    "SnapType": "periodic", 
    "CreateTime": 1496298697, 
    "ImageCount": 5
}
```

