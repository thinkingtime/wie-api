---
layout: docs
title: 通讯录API
prev_section: installation
next_section: structure
permalink: /docs/contact/
---


**一点说明**

该文档提供通讯录的查询接口，通讯录管理(新增，删除，好友分组等)部分在即时通讯中完成，需要客户端根据XMPP协议直接和即时通讯服务器通信：[即时通讯接口API]()

* [全部好友列表](#contact_list) 
* [通讯录群列表](#contact_group_list)
* [群成员列表](#contact_group_friend_list)

###获取全部好友列表###
**方法说明：**

>获取全部好友列表<a name=contact_list></a>

**服务器端接口方法**  

    /contact/list.do
**HTTP请求方式：**

    POST
**参数：**

    KAMS_TOKEN
**参数说明：**

参数名|参数说明|是否必须|
|-----|-----|-----|
KAMS_TOKEN|用户token|是
**服务器返回：**

**返回值类型：**

    json
示例：
```json
{
    "friendList":[
        {
            "position":"",//职位
            "headImg":"uploadfile/imgFile//1387890771279/1387890771279.jpg",//头像
            "nick":"聂运富",//昵称
            "email":"nieyf@FOUNDER.COM.CN",//email
            "name":"nieyunfu",
            "jid":"nieyf.founder.com.cn@wie-test",//即时通讯id
            "mobile":"13810731057"
        },
        {
            "position":"",
            "headImg":"",
            "nick":"邵建华",
            "email":"shaojh@FOUNDER.COM.CN",
            "name":"shaojianhua(邵建华)",
            "jid":"shaojh.founder.com.cn@wie-test",
            "mobile":"13810731057"
        },
        .....
    ],
    "success":true
}
```
     "success":服务器处理状态，可能的值{true,false},服务器抛出exception，该值为false；其它情况为true；

###获取通讯录群列表###<a name=contact_group_list></a>
**方法说明：**

**获取通讯录群列表**

**服务器端接口方法**

    /contact/group.do
**HTTP请求方式：**

    POST
**参数：**

    KAMS_TOKEN
**参数说明：**

参数名|参数说明|是否必须
|---|---|---
KAMS_TOKEN|用户token|是
**服务器返回：**

**返回值类型：**

    json
返回结果示例：
```json
{
    "groupList":[
        "好友",
        "Friends",
        "同事",
        "haoyou",
        "技术部"
    ],
    "success":true
}
```
     "success":服务器处理状态，可能的值{true,false},服务器抛出exception，该值为false；其它情况为true；

###获取群成员列表###<a name=contact_group_friend_list></a>
**方法说明：**

**获取群成员列表**

**服务器端接口方法**

    /contact/groupFriend.do
**HTTP请求方式：**

    POST
**参数：**

    KAMS_TOKEN
**参数说明：**

参数名|参数说明|是否必须
|---|---|---
KAMS_TOKEN|用户token|是
groupName|	群名称|	是
**服务器返回：**

**返回值类型：**

    json
返回结果示例：
```json
{
    "groupFriendList":[
        {
            "position":"",
            "headImg":"",
            "nick":"韦婷玉",
            "email":"weity@FOUNDER.COM.CN",
            "name":"weitingyu(韦婷玉)",
            "jid":"weity.founder.com.cn@wie-test",
            "mobile":"15026446836"
        },
        {
            "position":"",
            "headImg":"",
            "nick":"邵建华",
            "email":"shaojh@FOUNDER.COM.CN",
            "name":"shaojianhua(邵建华)",
            "jid":"shaojh.founder.com.cn@wie-test",
            "mobile":"13810731057"
        }
        .....
    ],
    "success":true
}
```
     "success":服务器处理状态，可能的值{true,false},服务器抛出exception，该值为false；其它情况为true；