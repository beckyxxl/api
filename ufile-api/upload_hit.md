====== 秒传文件 - UploadHit ======
{{indexmenu_n>40}}

秒传

说明：先判断待上传文件的hash值，如果UFile中可以查到此文件，则不必再传文件本身。

Requests

Syntax:

<code>
POST /uploadhit?Hash=<hash_value>&FileName=<file_name>&FileSize=<filesize> HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: <token>
</code>
Request Parameters

Request Headers

^Name         ^Type  ^Description^Required^
|Authorization|String|上传请求的授权签名  |Yes     |

Request Elements

^Name    ^Type  ^Description          ^Required^
|Hash    |String|待上传文件的ETag,详见ETag生成文档|Yes     |
|FileName|String|Bucket中文件的名称         |Yes     |
|FileSize|String|待上传文件的大小             |Yes     |

Reponses

Response Headers

^Name          ^Type   ^Description     ^
|Content-Length|Integer|响应body部分的长度     |
|X-SessionId   |String |请求失败时返回本次请求的会话Id|

Response Elements

^Name   ^Type   ^Description^
|RetCode|Integer|执行失败时的错误码  |
|ErrMsg |String |执行失败时的错误消息 |

> 注意: 成功执行只会返回HTTP 200回应,不带body数据.

Example

Example Request:

<code>
POST /uploadhit?Hash=AQAAABP9DJdoo2X0hKyax2pVTLQPaVzH&FileName=demofile&FileSize=1234 HTTP/1.1
Host: <bucket_name>.cn-bj.ufileos.com
Authorization: UCloud demouser@ucloud.cn13424346821929713944:S5FVD2w613MKb/hisjaqHdjvn9U=
Content-Length: 0
</code>
Example Response:

<code>
HTTP/1.1 200 OK
Content-Length: 0
</code>

