---
layout: docs
title: 资讯API
prev_section: installation
next_section: structure
permalink: /docs/news/
---
* [全部资讯类型](#getAllCategory)  
* [资讯列表](#news_list)

<a name="getAllCategory"></a>  
**获取全部资讯类型：**  
**方法说明：**

    该方法用于获取全部资讯类型信息

**服务器端接口方法：**

    /news/getAllCategories.do

**HTTP请求方式：**

    GET
**参数：**

    无
**参数说明：**

参数名|参数说明|是否必须|
|-----|-----|-----|
**服务器返回：**

**返回值类型：**

    json
示例：
```
{
    "categoryList":[
        {
            "id":106,
            "name":"要闻",
            "defaultView":true
        },
        {
            "id":55,
            "name":"资讯",
            "defaultView":true
        },
        .....
    ],
    "success":"true"
}
```
    "success":服务器处理状态，可能的值{true,false},服务器抛出exception，该值为false；其它情况为true；"categoryList"：资讯类型列表；

<a name="news_list"></a>   
**根据类型id获取资讯列表：**   
**方法说明：**

    该方法用于获取资讯列表

**服务器端接口方法：**

    /news/{categoryId}/{pageNo}/{pageSize}/{tt_news}.do

**HTTP请求方式：**

    GET
**参数：**

    categoryId, tt_news, pageNo, pageSize
**参数说明：**  

参数名:|参数说明|:是否必须|
|-----|-----|-----|
categoryId|资讯类型|是
tt_news|时间戳，获取该时间之前的资讯|是
pageSize|每页显示记录数|是
pageNo|页数|是
**服务器返回：**  

**返回值类型：**

    json
示例：
```
{
    "success":"true",
    "totalNum":208,
    "page":1,
    "newsList":[
        {
            "id":545,
            "title":"湖南•株洲第十一届心脑血管病学术会议召开",
            "introduction":"600多名学者参加株洲恺德心血管病医院举办的学术会议。",
            "picUrls":[
                "/uploadfile/imgFile//1388062045165/湖南株洲第十一届心脑血管病暨第一届小儿先心病学术会议现场_cut_1388062057395.jpg"
            ],
            "coverUrls":[
                "/uploadfile/imgFile//1388062045165/湖南株洲第十一届心脑血管病暨第一届小儿先心病学术会议现场_cut_1388062052672.jpg"
            ],
            "commentNum":5,
            "picNum":0,
            "releaseTime":1388062066000,
            "infoType":1,
            "categoryName":"资讯",
            "praiseNum":0,
            "uvnum":0,
            "pvnum":0
        },
        .....
    ], 
    "hotNewsList":[
        {
            "id":534,
            "title":"北大资源•梦想城首开盘热销7亿",
            "introduction":"北大资源•梦想城首次面世的2000套房源在短短三个小时之内售",
            "picUrls":[
                "/uploadfile/imgFile//1387784683213/北大资源_cut_1387784711318.jpg"
            ],
            "coverUrls":[
                "/uploadfile/imgFile//1387784683213/北大资源_cut_1387784704216.jpg"
            ],
            "commentNum":3,
            "picNum":1,
            "releaseTime":1387784751000,
            "infoType":2,
            "categoryName":"资讯",
            "praiseNum":0,
            "uvnum":0,
            "pvnum":0
        }
    ]
}
```
    "success":服务器处理状态，可能的值{true,false},服务器抛出exception，该值为false；其它情况为true；"totalNum"：总记录数；"newsList"：本次查询结果；"hotNewsList": 该类型下的焦点资讯；