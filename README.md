# 消息中心服务
本系统是基于laravel框架实现，laravel中文学习网站：http://www.golaravel.com/
# API接口说明
接口地址：/api

请求类型：POST

请求参数：

    {
        "method" : "",
        "data" : {},
    }
响应数据：

    {
        "status" : 200,
        "info" : "",
        "data" : ""
    }
消息系统接收邮件，rtx，微信发送请求，以下分别对这三种请求参数进行说明

## 邮件请求参数
    {
        "method" : "email",
        "data" : {
            "from" : ["a@xx.com","b@xx.com"],
            "to" : ["c@xx.com","d@xx.com"],
            "title" : "邮件标题",
            "body" : "邮件正文"
        }
    }
#### 参数说明
> * method ：请求服务方法，email表示请求发送邮件，必填参数
> * data ：请求数据，键值对数组格式，必填参数
> * from ： 发送者邮箱，可以是单个邮箱也可以是邮箱数组，选填参数，默认“OA系统邮件”
> * to ：接收者邮箱，可以是单个邮箱也可以是邮箱数组，必填参数
> * title ：邮件标题，必填参数
> * body ：邮件正文，必填参数

## rtx请求参数
    {
        "method" : "rtx",
        "data" : {
            "to" : ["huali","abao"],
            "title" : "rtx消息标题",
            "body" : "rtx消息内容",
            "autoclose" : 0
        }
    }
#### 参数说明
> * method ：请求服务方法，rtx表示请求发送rtx消息，必填参数
> * data ：请求数据，键值对数组格式，必填参数
> * to ：接收者花名拼音，可以是单个用户也可以是用户数组，必填参数
> * title ：rtx标题，必填参数
> * body ：rtx消息内容，必填参数
> * autoclose ：通知窗口自动关闭时间，单位秒，如果为0则不自动关闭，选填参数，默认0

## 微信请求参数
    {
        "method" : "wechat",
        "data" : {
            "appid" : 0,
            "to" : ["huali","abao"],
            "body" : "微信消息内容",
            "type" : 0,
            "is_private" : 0
        }
    }
#### 参数说明
> * method ：请求服务方法，wechat表示请求发送微信消息，必填参数
> * data ：请求数据，键值对数组格式，必填参数
> * appid ：应用id，选填参数，默认0
> * to ：接收者花名拼音，可以是单个用户也可以是用户数组，必填参数
> * body ：微信消息内容（纯文本），必填参数
> * type ：用户类型，单个用户0，部门用户1，分组标签的用户2，选填参数，默认0
> * is_private ：是否为保密消息，选填参数，默认0
## 响应数据字段说明
> * status ：响应状态码，200为成功，非200为失败，参照http状态码
> * info ：响应字符串，一般为提示信息
> * data ：响应内容，支持数字，字符串，数组

    
