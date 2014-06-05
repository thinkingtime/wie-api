---
layout: docs
title: 首页API
prev_section: installation
next_section: structure
permalink: /docs/main/
---

**获取首页模块信息：**  
**方法说明：**

    该方法用于获取全部资讯类型信息

**服务器端接口方法：**

    /index/main.do
**HTTP请求方式：**

    GET
**参数：**

    tt_news  

**参数说明：**

参数名|参数说明|是否必须|
|-----|-----|-----|
tt_news|时间戳，查询发布时间在此后的资讯|否
**服务器返回：**

**返回值类型：**

json
示例：
```
{
    "success":"true",
    "hotNewsList":[//热点资讯列表
        {
            "id":534,//资讯id
            "title":"北大资源•梦想城首开盘热销7亿",//资讯标题
            "introduction":"北大资源•梦想城首次面世的2000套房源在短短三个小时之内售",//资讯简介
            "picUrls":[//资讯图片
                "/uploadfile/imgFile//1387784683213/北大资源_cut_1387784711318.jpg"
            ],
            "coverUrls":[//封面图片
                "/uploadfile/imgFile//1387784683213/北大资源_cut_1387784704216.jpg"
            ],
            "commentNum":3,//评论数
            "picNum":1,//图片数量
            "releaseTime":1387784751000,//发布时间
            "infoType":2,//资讯分类：1为单图资讯，2为热点资讯，3为三图资讯，4为视频资讯'
            "categoryName":"资讯",//类别名称
            "praiseNum":9,//点赞数
            "uvnum":49,//浏览用户数
            "pvnum":143//浏览数
        },
        .....
    ],
    "moduleList":[//功能模块列表
        {
            "id":2,//模块id
            "moduleName":"消息",//模块名称
            "moduleCode":"MOD_MESSAGES",//
            "moduleType":"BASIC_FUNCS",
            "isValid":"T",
            "moduleUrl":"",//功能模块地址
            "moduleDesc":"消息",//功能模块描述
            "moduleLogo":null,//功能模块logo地址
            "moduleLogoActive":null,//功能模块按下图标
            "defaultSelected":"F",//是否默认显示
            "orderNo":10010,
            "installedNum":0//安装量
        },
        {
            "id":3,
            "moduleName":"通讯录",
            "moduleCode":"MOD_CONTACTS",
            "moduleType":"BASIC_FUNCS",
            "isValid":"T",
            "moduleUrl":null,
            "moduleDesc":"通讯录",
            "moduleLogo":null,
            "moduleLogoActive":null,
            "defaultSelected":"F",
            "orderNo":10020,
            "installedNum":0
        },
       .....
    ],
    "newsList":[//资讯列表
        {
            "id":543,
            "title":"中国科协会员日活动走进方正国际",
            "introduction":"“2013中国科协会员日”活动特别走进方正国际",
            "picUrls":[
                "/uploadfile/imgFile//1388050211409/DSC_0015_cut_1388050250708.JPG"
            ],
            "coverUrls":[
                "/uploadfile/imgFile//1388050211409/DSC_0015_cut_1388050234787.JPG",
                "/uploadfile/imgFile//1388050211409/DSC_0015_cut_1388050250708.JPG"
            ],
            "commentNum":18,
            "picNum":0,
            "releaseTime":1388050315000,
            "infoType":1,
            "categoryName":"要闻",
            "praiseNum":2,
            "uvnum":105,
            "pvnum":104
        },
        .....
    ]
}
```
>"success":服务器处理状态，可能的值{true,false},服务器抛出exception，该值为false；其它情况为true；"hotNewsList"：热点资讯列表；"moduleList"："功能模块列表"；"newsList"："资讯列表(不包括热点资讯)"；