# monitor——主服务(http://127.0.0.1:8000)
## 1. 登录服务
### 1. 登录
* url地址：/login
* 请求方式：post
* 参数：
```$xslt
account:root
password:1
```  
* 返回格式（成功）：
```$xslt
{
    "data": {
        "account": "root",
        "createTime": "2018-11-24 15:28:45",
        "email": "2922470093@qq.com",
        "mobile": 10087,
        "password": null,
        "updateTime": "2019-01-22 14:21:17",
        "userId": "3cd08494-fdb3-11e8-85c0-00163e0097c7"
    },
    "message": "成功",
    "success": true
}
```
* 返回格式（失败）：
```$xslt
{
	"data": null,
	"message": "密码错误",
	"success": false
}
```

### 2. 注册
* url地址：/regist
* 请求方式：post
* 参数：
```$xslt
account:dd
password:1
email:123@qq.com
mobile:10086
```
* 返回格式（成功）：
```$xslt
{
    "data": null,
    "message": "成功",
    "success": true
}
```
* 返回格式（失败）：
```$xslt
{
    "data": null,
    "message": "邮箱已被注册",
    "success": false
}
```

### 3. 获取个人信息
* url地址：/userInfo
* 请求方式：post
* 参数：
```$xslt
userId:0b646c1e-2433-11e9-9e5f-00163e0097c7
```
* 返回格式（成功）：
```$xslt
{
    "data": {
        "account": "root",
        "createTime": "2018-11-24 15:28:45",
        "email": "2922470093@qq.com",
        "mobile": 10087,
        "password": "c4ca4238a0b923820dcc509a6f75849b",
        "updateTime": "2019-01-22 14:21:17",
        "userId": "3cd08494-fdb3-11e8-85c0-00163e0097c7"
    },
    "message": "成功",
    "success": true
}
```
* 返回格式（失败）：
```$xslt
{
    "data": null,
    "message": "操作非本人数据，请重试",
    "success": false
}
```

### 4. 修改个人信息
* url地址：/edit
* 请求方式：post
* 参数：
```$xslt
userId:0b646c1e-2433-11e9-9e5f-00163e0097c7
account:dd
email:1234@qq.com
mobile:10086
```
* 返回格式（成功）：
```$xslt
{
    "data": null,
    "message": "成功",
    "success": true
}
```
* 返回格式（失败）：
```$xslt
{
    "data": null,
    "message": "邮箱已被注册",
    "success": false
}
```

### 5. 发送邮件
* url地址：/sendEmail
* 请求方式：post
* 参数：
```$xslt
email:123@qq.com
```
* 返回格式（成功）：
```$xslt
{
    "data": null,
    "message": "已经发送找回密码安全码到您邮箱。请在30分钟内重置密码",
    "success": true
}
```
* 返回格式（失败）：
```$xslt
{
    "data": null,
    "message": "该邮箱尚未注册",
    "success": false
}
```

### 6. 修改密码
* url地址：/reset
* 请求方式：post
* 参数：
```$xslt
secretKey:KEPC
email:2922470093@qq.com
password:1
```
* 返回格式（成功）：
```$xslt
{
    "data": null,
    "message": "成功",
    "success": true
}
```
* 返回格式（失败）：
```$xslt
{
    "data": null,
    "message": "安全码或邮箱不正确,请重新申请",
    "success": false
}
```

## 2. 监控任务服务
### 1.创建监控任务
* url地址：/addMonitor
* 请求方式：post
* 参数：
```$xslt
userId:0b646c1e-2433-11e9-9e5f-00163e0097c7
name:监控项目6
url:www.baidu.com
watchTime:10
type:1
warnMethod:1
```
* 返回格式（成功）：
```$xslt
{
    "data": null,
    "message": "成功",
    "success": true
}
```
* 返回格式（失败）：
```$xslt
{
    "data": null,
    "message": "邮箱已被注册",
    "success": false
}
```

### 2.关闭/开启监控任务
* url地址：/closeMonitor
* 请求方式：post
* 参数：
```$xslt
monitorId:73db27b5-1314-11e9-a14c-00163e0097c7
state:1
```
state：启用状态 0-禁用 1-启用
* 返回格式（成功）：
```$xslt
{
    "data": null,
    "message": "成功",
    "success": true
}
```
* 返回格式（失败）：
```$xslt
{
    "data": null,
    "message": "邮箱已被注册",
    "success": false
}
```

### 3.修改监控任务配置
* url地址：/editMonitor
* 请求方式：post
* 参数：
```$xslt
monitorId:2aff34b7-1316-11e9-8f76-00163e0097c7
userId:0b646c1e-2433-11e9-9e5f-00163e0097c7
name:项目1
url:www.baidu.com
watchTime:19
type:1
warnMethod:1
```
* 返回格式（成功）：
```$xslt
{
    "data": null,
    "message": "成功",
    "success": true
}
```
* 返回格式（失败）：
```$xslt
{
    "data": null,
    "message": "邮箱已被注册",
    "success": false
}
```

### 4.查询用户创建的监控任务
* url地址：/getMonitors
* 请求方式：post
* 参数：
```$xslt
userId:0b646c1e-2433-11e9-9e5f-00163e0097c7
pageNum:1
pageSize:10
```
* 返回格式（成功）：
```$xslt
{
    "data": {
        "endRow": 2,
        "firstPage": 1,
        "hasNextPage": false,
        "hasPreviousPage": false,
        "isFirstPage": true,
        "isLastPage": true,
        "lastPage": 1,
        "list": [
            {
                "createTime": "2019-01-30 15:09:18",
                "monitorId": "2372d193-245a-11e9-9e5f-00163e0097c6",
                "name": "第二次监控",
                "state": 1,
                "type": 1,
                "updateTime": "2019-01-30 15:09:23",
                "url": "www.qq.com",
                "userId": "0b646c1e-2433-11e9-9e5f-00163e0097c7",
                "warnMethod": 2,
                "watchTime": 10
            },
            {
                "createTime": "2019-01-22 14:41:57",
                "monitorId": "2372d193-245a-11e9-9e5f-00163e0097c7",
                "name": "第一次监控",
                "state": 1,
                "type": 1,
                "updateTime": "2019-01-30 14:41:57",
                "url": "www.baidu.com",
                "userId": "0b646c1e-2433-11e9-9e5f-00163e0097c7",
                "warnMethod": 1,
                "watchTime": 1
            }
        ],
        "navigateFirstPage": 1,
        "navigateLastPage": 1,
        "navigatePages": 8,
        "navigatepageNums": [
            1
        ],
        "nextPage": 0,
        "pageNum": 1,
        "pageSize": 5,
        "pages": 1,
        "prePage": 0,
        "size": 2,
        "startRow": 1,
        "total": 2
    },
    "message": "成功",
    "success": true
}
```
* 返回格式（失败）：
```$xslt
{
    "data": null,
    "message": "邮箱已被注册",
    "success": false
}
```

### 5.删除监控任务
* url地址：/delMonitor
* 请求方式：post
* 参数：
```$xslt
monitorId:2372d193-245a-11e9-9e5f-00163e0097c6
```
* 返回格式（成功）：
```$xslt
{
	"data": null,
	"message": "成功",
	"success": true
}
```

### 6.根据monitorId查询监控任务详情
* url地址：/getMonitor
* 请求方式：post
* 参数：
```$xslt
monitorId:618f5eba-2e94-11e9-9e5f-00163e0097c7
```
* 返回格式（成功）：
```$xslt
{
    "data": {
        "averageResponseTime": null,
        "commitContent": null,
        "createTime": "2019-02-12 15:04:03",
        "matchContent": null,
        "matchTarget": null,
        "matchType": null,
        "monitorId": "618f5eba-2e94-11e9-9e5f-00163e0097c7",
        "name": "测试1",
        "requestMethod": "get",
        "state": 0,
        "type": "web",
        "updateTime": "2019-02-28 19:13:09",
        "url": "www.qq.com",
        "usable": null,
        "userId": "0b646c1e-2433-11e9-9e5f-00163e0097c7",
        "warnMethod": "mail",
        "watchTime": 100
    },
    "message": "成功",
    "success": true
}
```

### 7.根据monitorId查询监控任务的监控结果（分页）
* url地址：/getMonitorRes
* 请求方式：post
* 参数：
```$xslt
monitorId:f9c6191c-8e2c-4563-8f53-f782c6a3b41b
pageNum:1
pageSize:12
```
* 返回格式（成功）：
```$xslt
{
    "success": true,
    "message": "成功",
    "data": {
        "total": 98,
        "list": [
            {
                "createTime": "2019-04-04 11:22:29",
                "disabledReason": "不包含指定内容",
                "endTime": null,
                "monitorId": "f9c6191c-8e2c-4563-8f53-f782c6a3b41b",
                "others": null,
                "responseTime": 147,
                "resultId": "e07b6f08-5688-11e9-9e5f-00163e0097c7",
                "startTime": null,
                "status": 200,
                "usable": null
            },{……}
        ],
        "pageNum": 1,
        "pageSize": 12,
        "size": 12,
        "startRow": 1,
        "endRow": 12,
        "pages": 9,
        "prePage": 0,
        "nextPage": 2,
        "isFirstPage": true,
        "isLastPage": false,
        "hasPreviousPage": false,
        "hasNextPage": true,
        "navigatePages": 8,
        "navigatepageNums": [1,2,3,4,5,6,7,8],
        "navigateFirstPage": 1,
        "navigateLastPage": 8,
        "firstPage": 1,
        "lastPage": 8
    }
}
```