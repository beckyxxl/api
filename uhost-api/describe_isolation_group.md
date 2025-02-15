# 描述硬件隔离组-DescribeIsolationGroup

描述硬件隔离组

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](../summary/regionlist.html)|**Yes**|
|ProjectId|string|项目id|No|
|GroupId|string|要查询的硬件隔离组id|No|
|Offset|int|列表起始位置偏移量，默认为0|No|
|Limit|int|返回数据长度，默认为20，最大100|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|IsolationGroupSet|array|硬件隔离组集合|No|

## IsolationGroup
|Parameter name|Type|Description|Required|
|---|---|---|---|
|GroupName|string|硬件隔离组名称|No|
|GroupId|string|硬件隔离组id|No|
|SpreadInfoSet|array|每个可用区中的机器数量。参见数据结构SpreadInfo。|No|
|Remark|string|备注|No|

## SpreadInfo
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Zone|string|可用区信息|No|
|UHostCount|int|可用区中硬件隔离组中云主机的数量，不超过7。|No|

# Request Example
```
https://api.ucloud.cn/?Action=DescribeIsolationGroup
&Region=cn-zj
&GroupId=eoLEQOOy
&ProjectId=UAfwElsL
&Offset=4
&Limit=3
```

# Response Example
```
{
    "Action": "DescribeIsolationGroupResponse", 
    "IsolationGroupSet": [
        {
            "GroupName": "FfjAvODP", 
            "GroupId": "sYCGPSVa", 
            "SpreadInfoSet": [
                {
                    "UHostCount": 4, 
                    "Zone": "ckzKEzju"
                }, 
                {
                    "UHostCount": 4, 
                    "Zone": "JxJjJLEh"
                }, 
                {
                    "UHostCount": 1, 
                    "Zone": "vfeWwork"
                }, 
                {
                    "UHostCount": 7, 
                    "Zone": "mdDSKRtP"
                }, 
                {
                    "UHostCount": 8, 
                    "Zone": "ckmKtCkf"
                }, 
                {
                    "UHostCount": 8, 
                    "Zone": "fdyQiLJX"
                }, 
                {
                    "UHostCount": 6, 
                    "Zone": "bnpHtcVh"
                }, 
                {
                    "UHostCount": 7, 
                    "Zone": "tlgxSexx"
                }, 
                {
                    "UHostCount": 7, 
                    "Zone": "DknEPTTQ"
                }
            ]
        }, 
        {
            "GroupName": "waQcuepq", 
            "GroupId": "dUtmePjp", 
            "SpreadInfoSet": [
                {
                    "UHostCount": 2, 
                    "Zone": "RIkhPcmF"
                }, 
                {
                    "UHostCount": 6, 
                    "Zone": "ZZiDAcUQ"
                }, 
                {
                    "UHostCount": 6, 
                    "Zone": "LxwjPKkC"
                }, 
                {
                    "UHostCount": 6, 
                    "Zone": "EICjITTU"
                }, 
                {
                    "UHostCount": 4, 
                    "Zone": "LvRzXMqO"
                }, 
                {
                    "UHostCount": 1, 
                    "Zone": "hsNbrfIO"
                }, 
                {
                    "UHostCount": 6, 
                    "Zone": "vLxZmVpQ"
                }, 
                {
                    "UHostCount": 9, 
                    "Zone": "YaqMHcyT"
                }, 
                {
                    "UHostCount": 8, 
                    "Zone": "VkTcAsom"
                }, 
                {
                    "UHostCount": 7, 
                    "Zone": "osJUBzQs"
                }
            ]
        }, 
        {
            "GroupName": "BuRDNSMV", 
            "GroupId": "PNbUMSnT", 
            "SpreadInfoSet": [
                {
                    "UHostCount": 1, 
                    "Zone": "FqzxOwWF"
                }, 
                {
                    "UHostCount": 8, 
                    "Zone": "TYJXNABc"
                }, 
                {
                    "UHostCount": 2, 
                    "Zone": "TmifjmqF"
                }, 
                {
                    "UHostCount": 6, 
                    "Zone": "ynTmVgAX"
                }, 
                {
                    "UHostCount": 3, 
                    "Zone": "VpulfwsB"
                }, 
                {
                    "UHostCount": 8, 
                    "Zone": "GmkCwqKR"
                }, 
                {
                    "UHostCount": 9, 
                    "Zone": "dDKSifpU"
                }, 
                {
                    "UHostCount": 5, 
                    "Zone": "UrGHZufJ"
                }, 
                {
                    "UHostCount": 5, 
                    "Zone": "gUdvtgFE"
                }
            ]
        }, 
        {
            "GroupName": "GLKfEBHo", 
            "GroupId": "YRMkPcpS", 
            "SpreadInfoSet": [
                {
                    "UHostCount": 5, 
                    "Zone": "XHgsxqdg"
                }, 
                {
                    "UHostCount": 6, 
                    "Zone": "iRQKLaRj"
                }, 
                {
                    "UHostCount": 9, 
                    "Zone": "vFgPUUjt"
                }, 
                {
                    "UHostCount": 4, 
                    "Zone": "BNWmMVpg"
                }, 
                {
                    "UHostCount": 1, 
                    "Zone": "DeXHKBzt"
                }, 
                {
                    "UHostCount": 9, 
                    "Zone": "avAFYxlI"
                }, 
                {
                    "UHostCount": 3, 
                    "Zone": "sPwawXVS"
                }, 
                {
                    "UHostCount": 7, 
                    "Zone": "XPOommle"
                }, 
                {
                    "UHostCount": 8, 
                    "Zone": "sDVWXwoD"
                }, 
                {
                    "UHostCount": 8, 
                    "Zone": "NHWKWBmr"
                }
            ]
        }, 
        {
            "GroupName": "YQRxjUUP", 
            "GroupId": "KbqAWrnZ", 
            "SpreadInfoSet": [
                {
                    "UHostCount": 9, 
                    "Zone": "ybcvUHGg"
                }, 
                {
                    "UHostCount": 2, 
                    "Zone": "bNCfdMfU"
                }
            ]
        }, 
        {
            "GroupName": "PoNhklah", 
            "GroupId": "VvKIjAoJ", 
            "SpreadInfoSet": [
                {
                    "UHostCount": 1, 
                    "Zone": "jtsvJBwo"
                }, 
                {
                    "UHostCount": 2, 
                    "Zone": "amlZMtpF"
                }, 
                {
                    "UHostCount": 5, 
                    "Zone": "RqGIAweJ"
                }, 
                {
                    "UHostCount": 2, 
                    "Zone": "ZUmCMgmh"
                }, 
                {
                    "UHostCount": 7, 
                    "Zone": "DHLgKKsN"
                }, 
                {
                    "UHostCount": 1, 
                    "Zone": "khBlCYDN"
                }, 
                {
                    "UHostCount": 7, 
                    "Zone": "aKZoaKxv"
                }, 
                {
                    "UHostCount": 7, 
                    "Zone": "XKwieRxS"
                }, 
                {
                    "UHostCount": 1, 
                    "Zone": "ZztdlMSY"
                }, 
                {
                    "UHostCount": 3, 
                    "Zone": "beGvpfXk"
                }
            ]
        }, 
        {
            "GroupName": "SPFppiav", 
            "GroupId": "wYyaBPCv", 
            "SpreadInfoSet": [
                {
                    "UHostCount": 2, 
                    "Zone": "sHRTtqXY"
                }, 
                {
                    "UHostCount": 6, 
                    "Zone": "IOyDEHtK"
                }, 
                {
                    "UHostCount": 2, 
                    "Zone": "qCWALWUq"
                }, 
                {
                    "UHostCount": 4, 
                    "Zone": "xWfLsowE"
                }, 
                {
                    "UHostCount": 2, 
                    "Zone": "hpvNNHce"
                }, 
                {
                    "UHostCount": 5, 
                    "Zone": "cJUybjFR"
                }, 
                {
                    "UHostCount": 2, 
                    "Zone": "mVDidZHk"
                }, 
                {
                    "UHostCount": 2, 
                    "Zone": "zbyPAXxR"
                }, 
                {
                    "UHostCount": 6, 
                    "Zone": "PxaozvKP"
                }, 
                {
                    "UHostCount": 5, 
                    "Zone": "BPfzdZlb"
                }
            ]
        }, 
        {
            "GroupName": "GhNYJpke", 
            "GroupId": "cILearzD", 
            "SpreadInfoSet": [
                {
                    "UHostCount": 4, 
                    "Zone": "NlJbuwsv"
                }, 
                {
                    "UHostCount": 6, 
                    "Zone": "JiDJVDmu"
                }, 
                {
                    "UHostCount": 3, 
                    "Zone": "reyxDucL"
                }, 
                {
                    "UHostCount": 5, 
                    "Zone": "BCanlmvA"
                }, 
                {
                    "UHostCount": 4, 
                    "Zone": "ahWxmqUD"
                }, 
                {
                    "UHostCount": 9, 
                    "Zone": "JxDibZhh"
                }, 
                {
                    "UHostCount": 1, 
                    "Zone": "TjYOutYX"
                }
            ]
        }, 
        {
            "GroupName": "chrixSUu", 
            "GroupId": "ppLfBQrd", 
            "SpreadInfoSet": [
                {
                    "UHostCount": 2, 
                    "Zone": "HPCwJiXb"
                }, 
                {
                    "UHostCount": 4, 
                    "Zone": "QUqJKHmy"
                }
            ]
        }, 
        {
            "GroupName": "UPZRkjRv", 
            "GroupId": "ZRjkgaqr", 
            "SpreadInfoSet": [
                {
                    "UHostCount": 1, 
                    "Zone": "CXNrjCEU"
                }, 
                {
                    "UHostCount": 8, 
                    "Zone": "aYcMlSSf"
                }, 
                {
                    "UHostCount": 9, 
                    "Zone": "gorleIqQ"
                }, 
                {
                    "UHostCount": 2, 
                    "Zone": "WSpdvKHZ"
                }
            ]
        }
    ], 
    "RetCode": 0
}
```

