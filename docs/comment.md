---
layout: docs
title: 评论API
prev_section: installation
next_section: structure
permalink: /docs/comment/
---

* [新增评论](#add)  
* [一级评论列表](#comment_list_1)  
* [子评论列表](#comment_list_2)

**新增评论：**<a name="add"></a>  
**服务器端接口方法**

    /comment/add.do

**HTTP请求方式：**

    POST
**参数：**

    resourceType, resourceId, content,KAMS_TOKEN
**参数说明：**

参数名|参数说明|是否必须|
|-----|-----|-----|
resourceType|评论类型(资讯评论为11，活动评论为2)|是
resourceId|资讯/活动id|是
content|评论内容|是
KAMS_TOKEN|用户token|是
**服务器返回：**

**返回值类型：**

json
示例：
```
{
    "comment":{
        "createTime":1395127431798,
        "resourceName":null,
        "replyNum":0,
        "authorId":26,
        "praiseNum":0,
        "isRead":"F",
        "resourceId":600,
        "categoryId":null,
        "resourceType":11,
        "displayInMymsg":"T",
        "words":null,
        "imgUrl":"uploadfile/imgFile/userHeadImgFile//20140306/1f4b06c2f1994d1095d8b207a13c622e.png",
        "authorName":"wangbinsh",
        "typeName":null,
        "content":"【回复】腾讯一出手，寸早不生。1_2014-03-18 15:23",
        "status":0,
        "id":620,
        "new":false
    },
    "success":"true"
}
```
     "success":服务器处理状态，可能的值{true,false},服务器抛出exception，该值为false；其它情况为true；"comment"：回复内容；

**获取(资讯|活动)一级评论列表：**<a name="comment_list_1"></a>  
**方法说明：**

    该方法用于查询资讯|活动的一级评论

**服务器端接口方法：**

    /comment/getComment.do

**HTTP请求方式：**

    GET
**参数：**

    resourceType, resourceId, pageSize, pageNo, KAMS_TOKEN
**参数说明：**

参数名|参数说明|是否必须|
|-----|-----|-----|
resourceType|评论类型(资讯评论为11，活动评论为2)|是
resourceId|资讯/活动id|是
pageSize|每页显示记录数|是
pageNo|页数|是
KAMS_TOKEN|当前用户token|否
**服务器返回：**

**返回值类型：**

    json
示例：
```
{
    "success":"true",
    "comments":[
        {
            "typeName":null,//类型名称
            "content":"dsadsadsa",//评论内容
            "resourceType":11,//资源类型
            "parentUserId":0,//上级评论用户id
            "status":0,//状态
            "authorName":"汪滨",//用户昵称
            "subComments":[//子评论列表
                {
                    "typeName":null,
                    "content":"城标厅",
                    "resourceType":11,
                    "parentUserId":0,
                    "status":0,
                    "authorName":"汪滨",
                    "subComments":null,
                    "subCommentSize":null,
                    "firstLevelId":502,
                    "displayInMymsg":"T",
                    "parentUserName":"汪滨",
                    "resourceName":null,
                    "parentId":0,
                    "replyNum":0,
                    "authorId":26,
                    "praiseNum":0,
                    "createTime":1395025188000,
                    "resourceId":623,
                    "words":null,
                    "imgUrl":"uploadfile/imgFile/userHeadImgFile//20140306/1f4b06c2f1994d1095d8b207a13c622e.png",
                    "isRead":"F",
                    "id":505,
                    "mine":false,
                    "new":false
                },
                {
                    ...
                }
            ],
            "subCommentSize":2,//子评论数
            "firstLevelId":null,//一级评论id
            "displayInMymsg":"T",//是否在我的消息中显示，T：显示、F：不显示
            "parentUserName":null,//上级评论用户昵称
            "resourceName":null,//资源名称，如资讯标题
            "parentId":null,//上级评论id
            "replyNum":3,//冗余字段，暂不用
            "authorId":26,//用户id
            "praiseNum":1,//点赞数
            "createTime":1395024934000,//评论时间
            "resourceId":623,//资源id
            "words":null,//包含的敏感词，暂不用
            "imgUrl":"uploadfile/imgFile/userHeadImgFile//20140306/1f4b06c2f1994d1095d8b207a13c622e.png",
            "isRead":"F",//是否已读
            "id":502,//评论id
            "mine":false,
            "new":false
        },
        {
            ...
        }        
    ],
    "size":2
}
```
    "success":服务器处理状态，可能的值{true,false},服务器抛出exception，该值为false；其它情况为true；"comments"：评论列表；"size"：一级评论数量